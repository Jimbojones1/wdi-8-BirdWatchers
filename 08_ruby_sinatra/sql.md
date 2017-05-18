# SQL (Stanard Query Language)

> SQL is the universal language of all relational databases

All relational databases are controlled using SQL. Some databases make slight changes to their SQL implementations here and there but in general, SQL is a portable language that'll work with any relational database.

We use SQL to define database schemas and to send queries.

## Starting/Stopping/Restarting MySQL

To start, stop, or restart MySQL you can run one of these commands:

```
mysql.server start
mysql.server stop
mysql.server restart
```

Once the MySQL server daemon (program that runs in the background) is running you can access the CLI (or REPL) by running `mysql -u <username>`. By default a MySQL installation on a development machine will have a user named `root` with no password. In production you should create a unique user that only has permissions to edit the databases that you specify for security purposes.

Log into the MySQL command line by running `mysql -u root`

## Schemas

Once logged in you can manage your databases.

A schema is fancy name for the way in which data is organized. In a relational database you have tables and those tables have columns. Database tables can be altered but that must be done separately from a running web application. In other words, you can create or remove fields in a table's schema but you can't do it on the fly like you can with a NoSQL database like MongoDB.

Schemas are managed in web apps using Migrations. Migrations are files that define changes to a database's table structure. They are run in the order they are created and are managed by an ORM like ActiveRecord. The ORM keeps track of which migrations have been run and only runs the ones that are missing from your database. 

Your ORM will translate code into SQL to make changes to your database schema.

### View Databases

`show databases;` will show all of the databases in MySQL.

`use table_name;` will put you into the database you want to manage

`describe table_name` will describe the table schema

### Manual schema creation

Here's an example of creating the schema for a database for a todo list application. It will have two tables: users and todos. Here's how to create it:

```
mysql -u root # logs you into MySQL

create database todo_list; # Creates a new database
use todo_list; # Puts you in the todo_list database. All commands run here will apply to this database

# This will create a users table with an id, username, and password column.
# The command also specifies the column types
create table users(id int auto_increment primary key, username varchar(255), password varchar(255));

# This will create a todos table with an id for a primary key, content as a string to hold
# the todo content, and a user_id column which is a foreign key that relates to the primary key 
# of the users table. This foreign key creates the relation between the two tables
create table todos(id int auto_increment primary key, content varchar(255), user_id int foreign key references users(id));
```

## Managing data

With a schema defined for our database, we now want to manage data. Normally you'd use code and an ORM to create, read, update, and delete data but behind the scenes your ORM is translating Ruby (or Python or PHP, or Node.js, or whatever) code into SQL that looks like this.

Here we're going to add some data to our`users` and `todos` tables and then pull that data back out in different ways including mashing together the results of multiple tables in a single query.

From here on out I'll be capitalizing the MySQL commands and lower casing the names of columns and other variable data so you can tell the difference between a MySQL-specific command and something unique to our schema.

```
# Add some new users to the users table
INSERT INTO users(username, password) VALUES('student', 'abc123');
INSERT INTO users(username, password) VALUES('instructor', 'password1');

# View all users in the table:
SELECT * FROM users;

# The previous command results in...
-------------------------------
| id | username   | password  |
|----|------------|-----------|
| 1  | student    | abc123    |
|----|------------|-----------|
| 2  | instructor | password1 |   |
-------------------------------

# Now we'll insert data into the todos table and associate it
# with user #1. Let's put a couple of todos in there to make
# some future queries more interesting
INSERT INTO todos(content, user_id) VALUES('Walk the fish', 1);
INSERT INTO todos(content, user_id) VALUES('Feed the baby', 1);
INSERT INTO todos(content, user_id) VALUES('Go to Texas', 2);

# View all todos
SELECT * FROM todos;

---------------------------------
| id | content        | user_id |
|----|----------------|---------|
| 1  | Walk the fish  | 1       |
|----|----------------|---------|
| 2  | Feed the baby  | 1       |
|----|----------------|---------|
| 3  | Go to Texas    | 2       |
---------------------------------

# Let's pull out all todos and user data and the todos belonging to user #1
# We're going to do this in one single query instead of two.

# First, let's see how we would do this using 2 queries:
SELECT * FROM users WHERE username='student';
SELECT * FROM todos WHERE user_id=1;

# The previous queries can be combined into one so we can get all
# the data at once.
SELECT users.username, users.password, todos.content, todos.user_id FROM users, todos, WHERE users.id=1 AND todos.user_id=1;

# The results...
--------------------------------------------------
| username | password | content        | user_id |
|----------|----------|----------------|---------|
| student  | abc123   | Walk the fish  | 1       |
|----------|----------|----------------|---------|
| student  | abc123   | Feed the baby  | 1       |
--------------------------------------------------
```

In that last query we see the details of a user and all of their todos as the result of a single query. We have two users in the database and each of those users have added items to the todos table but we're able to isolate all of a single user's details and their todos in one single query. We were able to cut down the number of queries from two queries into one.

That efficiency will translate into code. Rather than having to do things like this:

```ruby
user1 = User.find_by id: 1
user1_todos = user1.todos

# Here is where we'd have to manually put that data together
```

With the power of relational data powered by foreign key-primary key relations, we can do this instead:

```ruby
users_todos = User.find(1).todos
```

## Finding records by field

SQL is very powerful and we're only scratching the surface of it here. One last query type I want to leave you with is the `where` clause. This is a very powerful clause that lets you find records by any field and value. 

For example, let's find all users that have a user ID greater than 1 and then let's find all users that have a username of "student".

```
# assume we've started the mysql CLI and are using the todo_list
SELECT * FROM USERS WHERE id > 1;
SELECT * FROM USERS WHERE username='student';
```

## Conclusion

You'll likely not need to use SQL in your day to day work. Normally, you'll use it to verify that data has been added, updated, or deleted from your database tables. Beyond that, your ORM will handle everything you'd need to run CRUD operations.
