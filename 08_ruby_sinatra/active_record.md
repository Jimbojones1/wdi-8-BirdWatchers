# Active Record

> Setup and usage of ActiveRecord ORM

ActiveRecord is a database management pattern that the Ruby on Rails team codified into a Rubygem. The ActiveRecord gem has been ported to work with Sinatra through the [`sinatra-activerecord` gem](https://github.com/janko-m/sinatra-activerecord). This gem (library) allows you to connect to a variety of database engines, create models, and run CRUD actions through those models.

__IMPORTANT LINKS & RESOURCES__

- [Sinatra ActiveRecord dcss](https://github.com/janko-m/sinatra-activerecord)
- [ActiveRecord Query Interface](http://guides.rubyonrails.org/active_record_querying.html). Although this was written for Ruby on Rails, all of the same methods still apply because Sinatra-ActiveRecord is simply a port of the original ActiveRecord gem made to work with Sinatra. It works the same way in Sinatra as it does in Rails. Any differences will be documented here (there are very few)
- [SQLite Browser](http://sqlitebrowser.org) is a Mac application that lets you open Sqlite databases (`.sqlite` and `.sqlite3` files) and visually inspect your database table data.

## About Relational Database Engines

Before you install the `sinatra-activerecord` gem you have to decide which database engine you're going to use for your data. Unlike Node.js with it's default assumption that you'll use a non-relational, NoSQL database, Ruby applications traditionally use relational databases. Of course, the kind of database you use should be determined by the kind of data you'll be storing but for the sake of this lesson we'll be using a relational database. There are many relational database engines to choose from. The most popular are:

- __MySQL__ - A free and open source relational database engine developed by Oracle in the 90's. It is the most popular and widely used database engine in production environments
- __PostgreSQL__ - Another free and open source relational database engine developed by a computer science professor at UC-Berkely. In the past decade developers have started to rediscover its performance benefits and features that some other databases don't have and has begun to become a popular choice for developers whose language of choice is anything but PHP. Postgres is not as user-friendly as MySQL and so it is often difficult to introduce to new developes
- __SQLite__ is a light and portable free, open source relational database engine. It is most often embedded into iOS applications and used in cases where performance is not critical and the amount of data stored will be small. SQLite is easy to set up - you just create a `.sqlite` file - which is why it is almost always used as a development database for web applications.

In development mode SQLite is easy to work with so we'll be using it in our applications in development mode. When we launch our apps into production (on a live, public server) we'll use MySQL as it performs better in a production environment but requires additional setup steps that SQLite doesn't.

## Installation and Setup

> Let's get ActiveRecord installed and configured for Sinatra

### Installing it

Remember how we had to decide which database engine we want to use? Here's where this choice becomes important. Before we can use ActiveRecord we need to install a database driver gem for the database we'll be using. Since we're using SQLite in development mode, we'll need to install the SQLite3 gem in our `Gemfile`'s `:development` group. This will allow our app, or more specifically, ActiveRecord, to speak to SQLite databases. The database driver gem acts as a translator between the database engine and your ORM.

Once we've installed the driver we can focus on the ORM. We're using `sinatra-activerecord` in this case. So ActiveRecord is an ORM which translates Ruby code into SQL code that a database can understand and our database driver allows our ORM to connect to our database. The flow looks like this: `Ruby Code -> ORM -> Connect to DB via Driver -> ORM turns Ruby code into SQL on the connected DB`.

Your `Gemfile` should look like this:

```ruby
source 'https://rubygems.org'

gem 'bundler', '~> 1.12', '>= 1.12.5'
gem 'sinatra', '~> 1.4', '>= 1.4.7',               require: 'sinatra/base'
gem 'sinatra-activerecord', '~> 2.0', '>= 2.0.10', require: 'sinatra/activerecord'

group :development do
  gem 'rerun', '~> 0.11.0'
  gem 'sqlite3', '~> 1.3', '>= 1.3.11'
end
```

After editing your `Gemfile` run `bundle install` to install the newly added gems.

Now we're ready to start configuring ActiveRecord so it properly connects to our database.

### Configuration

__1 Create config files__

ActiveRecord uses a configuration file to do some of its work, especially in it's Rake tasks. So the first thing we need to do is create a config folder and a database YAML file. ActiveRecord expects these to exist to work. So first we run `mkdir config && touch config/database.yml`

Within the `database.yml` file we need a section for each environment that defines the database connection configuration for that environment. For now we only have a development environment so our `database.yml` file will look like this:

```yaml
development:
  adapter: sqlite3
  database: ../db.sqlite3
```

The Sinatra-ActiveRecord gem will automatically look for and read this file when it runs. The `development:` key specifies the environment the configuration is for. The `adapter` key specifies which database you're using (this lets it know which driver gem to use). Finally, the `database` key specifies the location of the database. Since this is an SQLite database it is stored in a regular file unlike MySQL or other databases which run on ports (like `mysql://username:password@localhost:3306/db_name`).

[You can learm more about YAML here](http://yaml.org)

__2 Add database tasks to your Rakefile__

Now that you have a configuration file set up you need to add the ActiveRecord Rake tasks to your Rakefile. This is as simple as requiring a library at the top of your `Rakefile` and running the database connection code.

At the top of your `Rakefile` add the following require statement:

```ruby
require 'sinatra/activerecord/rake'
```

Next, just below the require statement, you need to add code that connects to your database. ActiveRecord will connect to your database based on your environment (`ENV['RACK_ENV']`). By default your environment will be `development` unless otherwise specified. Now, add this code to create a connection to your database:

```ruby
ActiveRecord::Base.establish_connection(
    :adapter => 'sqlite3',
    :database => 'db.sqlite3'
  )
```

We can write this code in a way that will automatically choose the correct database configuration variabless but for now we're just hard coding the configuration. For now we're simply hard coding the SQLite3 adapter and manually specifying the database file for this SQLite database.

The require statement along with the database connection statement will make a set of new Rake rasks available to you and those tasks will take advantage of the database connection code to do their job.

At this point if you run `rake -T` you will see many more Rake tasks than you've actually defined in your Rakefile. These come from the `require` statement you added at the top of the Rakefile.

__3 Connect your application to the database__

At this point we have configured ActiveRecord and added some Rake tasks. Now we want our application to be able to take advantage of this database connection. To do this, open up your `config.ru` file and add the following code just after your `Bundler.require` statement:

```ruby
# config.ru
require 'bundler'
Bundler.require :default, ENV['RACK_ENV'].to_sym

ActiveRecord::Base.establish_connection(
    :adapter => 'sqlite3',
    :database => 'db.sqlite3'
  )

# Require models here

# Require controllers and middleware here

# Map (mount) controllers at paths here
```

By adding the `ActiveRecord::Base.establish_connection(...)` line to your `config.ru` file you are creating a persistent database connection that your application's models can use to communicate with the database.

__4 Create your database schema__

Now we'll use ActiveRecord's Rake tasks to create a database migration. Migration files are used to translate the code from your language of choice into something your database can understand. Migrations are files that are written in Ruby (they can be in any language but we're using Ruby in this case) that define your database schema. Here we're going to create a migration that creates a new database table and defines its columns. *Note that ActiveRecord will automatically create a primary key column called `id` for any new table you create. Migrations can be used to create, update, and destroy database tables.

Let's create a new users table:

First we'll create a migration file stub by using a Rake task then filling it out with the details we want. Run the following in your terminal:

```shell
rake db:create_migration NAME=create_users
```

This will create a new file in `db/migrate/<today's_date_migration_name>.rb`

Now open the file and you'll see the following:

```ruby
class CreateUsers < ActiveRecord::Migration
  def change
    # Your table schema here
  end
end
```

Inside of the `change` method we're going to add some code so that the final file looks like this:

```ruby
class CreateUsers < ActiveRecord::Migration
  def change
    create_table :users do |t|
      t.string :username
      t.string :password
    end
  end
end
```

What this is saying is: "Create a table called users with a string column called 'username' and a string column called 'password'". The primary key, `id`, will always be created automatically for you so you do not need to manually define it in your migration.

__5 Run migrations (set up the database)__

The final step to adding tables to our database is to run the migration file(s). To do this simply run `rake db:migrate` in your terminal and a new table will be added to your database. You can manually check to see if the migration worked as expected in a few ways:

- If there are no error messages then you should be fine
- Use the `sqlite` CLI to browse your database (not recommended - the MySQL CLI is the only database CLI we'll cover in class)
- Use the SQLite Browser application to open the `db.sqlite3` file and then navigate to the "Browse Data" tab to view the tables and the data within those tables in your database

### Models

Now we have a database connection within our app along with a ready-to-use database. All that's left is to define a model we can use to perform CRUD operations on your database.

First create a models folder in your app folder by running `mkdir app/models`.

Next let's create a User model. Create a new file by running `touch app/models/user.rb` and add the following code to it:

```ruby
class User < ActiveRecord::Base
  # You don't need to add any methods or attributes here but you can.
  # ActiveRecord comes with some helpful methods for validating data
  # before it gets saved to the database but for now an empty model
  # class is all you need to start storing data.
end
```

#### Model Relations

We can specify relations between models in code which translate directly into the same relations that are defined in the database tables using foreign keys and primary keys:

```ruby
class User < ActiveRecord::Base
  has_many :todos
end

class Todo < ActiveRecord::Base
  belongs_to :user
end
```

In the above code we use the relational methods `has_many` and `belongs_to`. Here our models are basically saying "A User has many todos" and "Each todo belongs to a single user".

### CRUD Actions on Models

Now we can use our User model to save users to our database in 2 easy steps.

1. Add a require statement *right before* you require your models in `config.ru` but *after the DB connection* code.
2. Now you have access to a `User` object in all of your controllers.

#### Example of how to save a new user to the database

Let's say you wanted to save a username and password from some URL parameters. Here's how to do it: (You should always use forms for this but we're gonig to use a simpler method for the sake of this example)

```ruby
# in config.ru
#
# By now you've required all your dependencies and controllers
# and we're in the mapping section of the file
map('/users') { run UsersController }
map('/') { run HomeController }
```

```ruby
# in app/controllers/users_controller.rb

class UsersController < ApplicationController
  get '/:username/:password/?' do |username, password|
    if username != '' && password != ''
      user = User.create username: username, password: password
    end

    if user
      'User was created'
    else
      'There was an error creating a user'
    end
  end
end
```

With the server running you can now visit [http://localhost:9292/users/<username>/<password>](http://localhost:9292/users/<username>/<password>) and a new user will have been created in your database.

Check out the [ActiveRecord Query Interface docs](http://guides.rubyonrails.org/active_record_querying.html) to learn more about the methods that ActiveRecord makes available to all of your models. There are methods for Creating, Reading, Updating, and Deleting database records.

## Conclusion

This is just the beginning. There is so much more that you can do with ActiveRecord in Sinatra. These notes only cover the basic installation, setup, and usage of a single model method. You can manage data in any way imaginable with the tools you just set up. Relational databses are powerful tools. Take advantage of them.
