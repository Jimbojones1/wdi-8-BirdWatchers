# Relational and Non-Relational Databases

> Today we'll talk about relational and non-relational databases

## Resources

These links may help you as read through these notes:

[MongoDB and NoSQL info](https://www.mongodb.com/nosql-explained) - This gives you an overview of what NoSQL is and how MongoDB fits into everything.

## Relational Data

Relational data can be thought of like Excel spreadsheets. The data is stored in rows and columns. A table is part of database that represents one coherent resource and its properties.

Another good way to think of relational data is to think about how the data in your favorite web applications are structured. Let's take Twitter for examples.

## Modeling Relational Data

__Example Time:__ Let's think about Twitter for a moment. How might the data in Twitter be structured?

- __Users__ - A database table which holds the data for an individual  user. When represented as a simple database table it would look like this:

```
--------------------------------------
|                 USERS              |
|------------------------------------|
| id | username | password | email   |
|----|----------|----------|---------|
| 1  | billp    | abc123   | x@x.com |
--------------------------------------

----------------------------
|           TWEETS         |
|--------------------------|
| id | content  | user_id  |
|----|----------|----------|
| 1  | my tweet | 1        |
----------------------------
```

As we can see, we're really simplifying the data inside Twitter. Let's explore these two tables and what they mean.

1. __Users__ - The `user` table holds the username, password, and email address. These hold string and text data types. The `id` property is what's called a primary key. A primary key is a unique, auto-incrementing integer. Keys of any type in a relational database allows queries to run faster. With any sort of key, here a Primary Key, the database engine will create a sort of quick index that allows users who use Keys/indexes to return data quicker than anyone.
2. __Tweets__ - The `tweet` table has three properties. The Tweet content, the user ID of the user who sent it out, and its own Primary Key, the `id`. The Tweet table will use the `id` as a primary key in the same way the `user` table uses them. Now there is a Foreign Key - the `user_id` column - that references the primary key of a column in a different table. Foreign Keys relate one or more rows in a database table to one or more tows in another table. In this case, the Tweets are stored separately from the users table but are linked to the user who published them using a Foreign Key relationship. The `user_id` (a Foreign Key) property contains the User ID of the user who Tweeted the Tweet originally. This allows the database to join together rows of two different database tables quickly. You can easily ask the database for all tweets belonging to a specific user or which user a specific Tweet belongs to.

## Types of Relationships

There are basicallt three kinds of database relations:

- Many to many
- Many to One
- One to mainy

An ORM makes it easy to define these relationships. Most ORMs will ask you to define the relationships between database tables in code. An ORM takes your language's code and data types and will convert it into SQL so that the database can understand what you're trying to do in code. It hides the SQL behind classes and Objects created in code.

A __many to many__ relationshp is when many rows in one table relate to many rows in another table. So in Twitter's case many users may have many Tweets.

A __many to one__ relationship is when many rows in one table relate to one row in another table. In Twitter's case, many tweets may belong to a single user.

In a __one to many__ relationship you have the reverse of a many to one relationship. So going along with Twitter, one user has many Tweets.

## Relational vs. Non-Relational Databases

A relational database stores relationships between data using foreign keys. In a non-relational database there are no relationships between data sets. Instead, the data is all held in a data type that's similar to a JavaScript object (a POJO). Any related data in a non-relational (NoSQL) database can be stored right alongside the data itself.

In a NoSQL or non-relational database the schema can be created on the fly.

### What is a Schema?

A database schema is the definition of how data is structured. Relational database systems like MySQL, PostgreSQL, or SQLite all have database tables with columns that are defined before they are accessed. With relational databases you must know what data and their types are needed in the database when it is first created. This doesn't mean a relational database schema cannot be changed at a later time. You can always update the database schema of a relational database but you must do it prior to have a web application's model access the data.

In a non-relational database the schema can be changed at run-time. What this means is that you can change the database's schema while the program runs. You can have one record that has a different schema than all the other records in the same "table". NoSQL has the concept of "documents" instead of tables that consist of rows and columns. These "documents" are stored in the equivalent of what a relational database would call a database. This is a dataset that contains a bunch of "documents" which are basically just JavaScript objects.

### When to use Relational or Non-Relational Databases

If your data would naturally fit into a spreadsheet (even if there could be relations between two sheets or tables in the spreadsheet) then your data is best used in a relational database. Someimtes, however, your data can be unpredictable and you may need to create new "columns" on the fly. In cases like these a non-relational, NoSQL database would be more useful.

### NoSQL and Node.js

You'll hear the term "MEAN stack" at some point when using Node. This is an acronymm that stands for __M__ongoDB, __E__xpress, __A__ngular.js, and __N__ode.js. The MEAN stack is similar to the LAMP stack but it runs on Node.js based technologies. Traditionally, Node.js applications use MongoDB or a similar NoSQL (non-relational) database as their storage. This is because NoSQL technologies use Node.js as their query language.

It's a mistake to use a NoSQL database with Node just because that's what's popular or standard however. It's important to take a look at your data and decide whether it fits into a relational or non-relational model. __Always use the right tool for the job__. Although NoSQL databses have traditionally been used alongside Node.js, you have to remember that Node is a new technology and there are now plenty of great options that allow you to use a relational database engine with your data.
