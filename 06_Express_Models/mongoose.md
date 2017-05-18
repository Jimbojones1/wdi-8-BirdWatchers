
## The Mongoose ODM

> An "ODM" is just like an ORM except they're used for non-relational databases

**Mongoose** connects our *application* to our MongoDB *database*. To add it as a dependency to our project, we just need to install it as follows:

`npm install mongoose --save`

Now, create a new folder in your project called `models`. Then, create a file called `db.js` -- this is where we're going to store our database specific files. *No actual models* will be in this file. Inside of our `db.js` file, we're going to require **Mongoose**:

`var mongoose = require('mongoose');`

**Connect to Mongo using Mongoose**
```javascript
// mongodb://username:password@localhost:27027/database-name
var connectionString = 'mongodb://localhost/test';

// connect to database
mongoose.connect(connectionString);
```

*Connect Error?* If you are getting a connection error, you may need to replace "localhost" with 127.0.0.1.

### Mongoose Events
These events tell us the status of our connection to MongoDB; this are *VITAL* to debugging.
- **connected**: connected to database
- **error**: an error has occured with the database
- **disconnected**: the connection to the server has been terminated

*Example*
```javascript
mongoose.connection.on('connected', function () {
  console.log('Mongoose connected to ' + connectionString);
});
mongoose.connection.on('error',function (error) {
  console.log('Mongoose connection error: ' + error);
});
mongoose.connection.on('disconnected', function () {
  console.log('Mongoose disconnected!');
});
```

### Including Your Database in your application
In your primary `app.js` file, we need to include our `/models/db.js` file. This will establish our connection to our database.

*app.js*
```javascript
// include mongodb via /models/db.js
require('./models/db');
```

## 4. "Documents", Schemas, and Models

MongoDB stores data in each database as **documents**. These documents are stored as **BSON**; this is just _binary_ JSON data. The tool that we're using to communicate with Mongo - **mongoose** takes this BSON data and turns it into JSON for our ease of use. *One of the primary advantages of using MongoDB with Javascript is that everything is essentially a Javascript object!*

Each time you create a **document** in MongoDB, it is given an
`_id`. MongoDB automatically creates this when each document is created and assigns it a unique ObjectId value. It can be considered the *primary key* of your Document.

#### Schema Data Types
MongoDB allows the following *schema* types inside of a `document`:
- String
- Number
- Date
- Boolean
- Buffer (binary information such as images and video)
- Mixed (mixed data)
- Array (arrays of the same data type *or* an array of nested sub-documents)
- ObjectID (used with `_id`)

### Building a Model with a Schema
Let's create a new file: `/models/tasks.js`; the following Schema will be placed inside of there.

We now need to model some data. For example, say we have a list of tasks we'd like to complete. We're going to store our **tasks** as documents in MongoDB. A task as a Javascript object would look like:

```javascript
var task = {
  name: "My task",
  description: "This is something I need to do",
  completed: false
};
```

We can use the `mongoose.Schema({});` method to create a schema.

```javascript
// require mongoose
var mongoose = require('mongoose');

var TaskSchema = new mongoose.Schema({
  name: String,
  description: String,
  completed: Boolean
});
```
Notice how we're declaring the *type* of data stored in the object. Say we want to have a default value, though. When you create a task, it is not completed yet, no?

```javascript
// require mongoose
var mongoose = require('mongoose');

var TaskSchema = new mongoose.Schema({
  name: String,
  description: String,
  completed: {type: Boolean, "default": false }
});

// export our Model for use in our node app// export!
module.exports = mongoose.model('Task', TaskSchema);
```
We put the word `default` in quotes because it is a reserved word in Javascript. All we've changed is adding a `default` value as well as specifying a `type` (based on what is allowed in the Schema).

Finally, to make our actual MVC-esque **model**, we need to tell Mongoose to create a model:

`var Task = mongoose.model('Task', TaskSchema);`
Where we declare `Task` as the new model name and assign a schema to this model.

## 5. Mongoose Query Methods

- `find`: General search based on a supplied query object
- `findById`: Look for a specific ID
- `findOne`: Get the first document to match the supplied query
- `geoNear`: Find places geographically close to the provided latitude and longitude
- `geoSearch`: Add query functionality to a geoNear operation

## 6. MongoDB CRUD

```javascript
var mongoose = require('mongoose');
var Task = require('../models/Tasks');

// get ALL items in an array
Task.find(function (err, tasks) {
  console.log(tasks)
});

// create an item
Task.create({ name: "task #1", description: "a simple task"}, function (err, task) {
  console.log(task);
});

// get a specific item by _id
Task.findById(id, function (err, task) {
  console.log(task);
});

// update a task by _id
Task.findByIdAndUpdate(id, { description: "updating this" }, function (err, task) {
  console.log(task);
});

// delete by _id
Task.findByIdAndRemove(id, { params: "object stuff" }, function (err, task) {
  console.log("Deleted:");
  console.log(task);
});
```

## More About Schemas

We know that schemas are the definitions of databases. In other words, they define the name of the database, the tables within it, what columns each table will have and their corresponding data type. In the world of relational databases this makes total sense but you might be asking yourself why a non-relational database would ever enforce a schema or even have one to begin with?

After all, isn't the whole point of NoSQL (non-relational databases) to be able to define documents with varying properties on the fly? If that's the case then why would we put constraints on our NoSQL database. __Doesn't that defeat the whole purpose of NoSQL?__

The answer is *yes*! It *does defeat the entire purpose* of NoSQL databases. But the creators of Mongoose were smart. They realized that in the real world, the vast majority of your database documents (or "entries" or "rows" if you want to use the relational DB terminology) are going to use the exact same property names and those object properties are almost always going to be of the same data type. 

By default, when you save any data into a MongoDB collection it will only store the data that matches your database model's schema and ignore any additional properties. Don't worry, though. There's a way to turn this strict schema enforcement off. Before I tell you how, let's talk about how MongoDB and Mongoose get used in the real world.

### Real world use case

From April of 2015 to February of 2016 there was a Chicago based company called Aplo that had created a health insurance enrollment platform that allowed people to purchase Affordable Care Act (Obamacare) health insurance plans. The company was working with both relational data (in the form of user accounts and such) and non-relational data (leads and or CRM type data).

The company's CRM features were powerful. There was a standard web form that users would fill out in order to create a new lead in our system. For most users, the standard web form worked fine and there was no reason to alter it. This data became part of the official MongoDB "leads" collection schema. Things like name, age, phone number, and mailing address were stored as documents in this collection.

For 75% of Aplo's users, the standard form was just fine. The other 25% however, needed to add additional information to the form. The web app let them do this in two different ways:

1. __Custom Fields__ was a feature that was added after many users complained that a very specific data point was no being captured in the standard web form. This feature worked by allowing users to press a button which then displayed two text boxes - one for the custom field name and one for the custom field value. So if a user wanted to track something very specific like a client's favorite color, they could easily create a `favorite_color` field for that particular client/lead of theirs. A user could create an unlimited amount of custom fields using this method.
2. __Handling Dependents__ was a difficult task. Users wanted to not only track information about one of their clients or leads but also that client/lead's family. How many form fields would you create for entering each client's child (which included their age and other personal information)? The company couldn't impose a limit to how many children could be entered into the system and using a relational database to pull out all of the different dependents a client could have (parents, grandparents, spouses, children, etc.) would be more complex than it was worth.

The solution to both of these issues were solved by creating additional fields in our MongoDB documents on the fly. __The point of this story__ is to explain __why a NoSQL database would have a schema__. Mongoose schemas allow you to ensure that the data you try to save can be validated.

So if your schema definition looks like this:

```js
var mongoose = require('mongoose'); // Require Mongoose library

// Create a new schema for the User model
var UserSchema = new mongoose.Schema({
  username: String,
  password: String,
  age:      Number
});

module.exports = mongoose.model('User', UserSchema);
```

...and the data you want to save looks like this:

```js
var newUser = {
  username: 'Willy',
  password: 12345,
  age:      29,
  height:   '6 feet, 0 inches'
}
```

Then what happens is that Mongoose will throw an error and the `height` property will be ignored. The error is thrown because the `password` is a `Number` rather than a string as defined by the schema and the `height` property is ignored because it is not part of the schema at all.

### Allow schema updates on the fly

We know that Mongoose, by default, does not allow you to stray from your model's schema which means you can only pass Mongoose objects that adhere to that schema and that it will ignore any additional properties that are not defined in the schema.

To change this default behavior you need to pass an optional configuration object to Mongoose's `.Schema` method. The configuration object has a property called `strict` that has two possible values: `true` or `false`. When set to `true` (the default), only object data matching the schema are saved. When set to `false` you can pass an object that contains additional properties not present in the schema and that data will be saved along with the predefined schema data.

#### Using the schema options

This is how to create a schema not in strict mode:

```js
// models/user.js
var UserSchema = new mongoose.Schema({
  username: String,
  password: String,
  age:      Number
}, {
  strict: false
});

module.exports = mongoose.model('User', UserSchema);
```

Notice the second object that was passed to the `.Schema` method. Again, here's that same code in a way that is easier to  follow:

```js
// models/user.js
// --------------
var mongoose = require('mongoose'); // Require Mongoose library

// The schema object
var schema = {
  username: String,
  password: String,
  age:      Number
};

// The options object
var schemaOpts = {
  strict: false
};

// Creating a new schema for the User model
var UserSchema = new mongoose.Schema(schema, schemaOpts);

// Create the User model
module.exports = mongoose.model('User', UserSchema);
```

As you can see, all we did here was add an options object to the schema creation method as its second optional parameter, setting the `strict` property to `false` which lets us bypass Mongoose's schema validation and lets us create new documents with properties that aren't officially a part of the Mongoose schema for a given model.

### Mongoose Conclusion

Now we know why we'd want to set a schema on a schema-less database and how to bypass the schema rules if we needed to using Mongoose. The [Mongoose documentation](http://mongoosejs.com/docs/guide.html) has a lot more information on its usage and options. Please be sure to check it out.

If you're looking for even more freedom and/or flexibility, you can [check out the native MongoDB driver for Node.js](https://github.com/mongodb/node-mongodb-native) which allows you to run queries on MongoDB but does not have any schema defining methods. __Be warned:__if you use a library we haven't covered in class then you're pretty much on your own. We'll provide support if we have the time or ability but you should stick to what we cover in class unless you're totally confident you can handle new material on your own.






