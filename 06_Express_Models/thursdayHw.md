# Building Express APIs

> Homework about APIs introducing you to Controllers, routes, and models

## Your Mission:

Create a basic web API from scratch using the Express framework. The API should have at a minimum:

- 1 Controller
- 2 Different URLs or paths in your controller (/api  or /api/:id are these the same?)
- One of the controller's paths should have methods for Creating, Reading/Listing, Updating, and Deleting the resource it is responsible for

## Remember:

- Models and Controllers are named after your resources
- Model file names are lower case and *singular*. You would have a `UserModel` model in a file called `user.js`, not a `UsersModel` inside of `users.js`
- Controller file names are lower cased and plural. You would have a `UsersController` controlling the path `http://localhost:3000/users` in a file at `controllers/users.js`. You would __NOT__ have a `UserController` controlling `http://localhost:3000/user` in a `user.js` file

__Models are Objects that represent one or more rows in a database__.

Mongoose is an ODM. An ODM is similar to an ORM. An ODM is an Object Document Mapper. It maps a representation of a MongoDB (or other NoSQL database) document and turns it into something that the database can understand. An ODM behaves like an ORM except on non-relational databases. They allow you to pass data to the library which then exposes methods for Creating, Updating, Reading, and Deleting.
