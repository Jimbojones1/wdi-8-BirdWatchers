## Mongo & Importing JSON to a Database


Read: [Mongo vs Sql](https://www.sitepoint.com/sql-vs-nosql-differences/)
#### Console w/MongoDB


## Installing mongodb
annotated version
#### echo prints a message to your terminal.
```
echo -e "*** Hi! This script will install MongoDB."
echo -e "You could be asked for your admin password up to four times."
# update homebrew
brew update
# use homebrew to install
echo -e "Installing MongoDB"
sudo brew install mongodb -Y
# create the mongodb swap directory
echo -e "Creating the MongoDB directory..."
sudo mkdir -p /data/db
# set read/write permissions for this directory to root
echo -e "Setting Permissions to the /data/* directory for MongoDB"
sudo chmod -777 /data/*
# start mongodb!
echo -e "Starting Mongod..."
sudo mongod
```



1. You must always do the following to run your database server
* To allow connections to your MongoDB database (such as applications needing to connect or Mongoose...), run `sudo mongod`. Think of it as `mongod` oversees **MongoDB**.
* To connect to the MongoDB terminal (similar to `psql`), enter the `mongo` command.

#### Console commands

* `help`:   Show help.
* `db.help()`:  Show help for database methods.
* `db.<collection>.help()`: Show help on collection methods. The <collection> can be the name of an existing collection or a non-existing collection.
* `show dbs`: Print a list of all databases on the server.
* `use <db>`: Switch current database to <db>. The mongo shell variable db is set to the current database, if no database it creates one.
* `show collections`: Print a list of all collections for current database
* `db.collectionName.find()`: Shows the documents in your collection.
* `show users`: Print a list of users for current database.
* `show roles`: Print a list of all roles, both user-defined and built-in, for the current database.
* `show profile`: Print the five most recent operations that took 1 millisecond or more.
* `show databases`: No description needed.
* `db.createCollection("phish")` : creates a collection named phish
* `db.phish.insert({"name": "little guy"})` : inserts a document into the phish collection
* `db.phish.find({"name": "little guy"}).pretty()` : queries the database for the document with name = little guy


#### Import JSON into a database


1.  This is in your terminal screen, not in mongo
```bash
# mongoimport --db <databaseName> --collection <collectionName> --file <jsonFile.json> --jsonArray
mongoimport --db --file phish --collection songs phish.json --jsonArray
```

Only use the `-jsonArray` flag if you are importing an array of objects! Otherwise, you don't need it!
