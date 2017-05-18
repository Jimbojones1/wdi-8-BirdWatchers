# Express from Scratch

> Everything you need to know to set up Express from scratch

## Resources

- An example web application set up in the way described on this page [can be found here](https://github.com/ga-chicago/express-bp2)
- [A Gulp Boilerplate](https://github.com/ga-chicago/gulp-boilerplate) shows how to set up Gulp tasks
- The [Handlebars documentation](http://handlebarsjs.com) will show you how to write Handlebars templates (for example, do things like looping over arrays and objects, output variables, unescape data, etc.)

## Contents:

- How Node apps are creates
- Project structure
- Gulp task setup
- Setting up Express
- Adding templates and views with Handlebars
- Creating routes
- Route parameters

## 4 Steps to a Node.js App

1. __`npm init` to initialize your project__ as a Node module or package (__do NOT__ pick a `name` that is the same as one of your dependencies or you'll get errors when installing them)
2. __Create your project structure.__ Create the files and folders you *know for sure* you'll be using in your application.
3. __Install required dependencies.__ Only install the packages you absolutely know you'll be using.
4. Write your code.

### Planning the app

It's important to plan your project before diving into the code. If we were to create a todo list application we could plan a simple one with the following features:

- It stores items in your todo list
- You may view more details about any todo item by clicking a link beside it
- You may add or remove a todo at any time (these steps will not be shown)

If we were to have such a simple application then we would likely have the following simple user flow:

1. User sees list of all todos on homepage
2. User can go to a todo item detail page by clicking a link
3. Form elements control the ability to add or remove todos from the list (not shown)

## Project structure

Be sure you've called `npm init` in your project's root to initialize it as a Node module.

Based on what we know about the application we know we'll need a project structure that looks like this:

```
todo_list/
  |
  |_ server/
  | |
  | |_ app.js
  | |
  | |_ public/
  | | |
  | | |_ css/
  | | |_ less/
  | | | |
  | | | |_ style.less
  | | |
  | | |_ js/
  | |   |
  | |   |_main.js
  | |
  | |_ views/
  |   |
  |   |_ layouts/
  |   | |
  |   | |_ main.hbs
  |   |
  |   |_ partials/
  |   | |
  |   | |_ header.hbs
  |   | |_ footer.hbs   
  |   |
  |   |_ home.hbs
  |   |_ detail.hbs
  |
  |_ .gitignore
  |
  |_ gulpfile.js
  |_ package.json
```

__IMPORTANT: Although we might *talk about* git repositories on this page, please *DO NOT* initialize a git repository when submitting your homework! Just include the `.gitignore` file and delete your `node_modules` folder before submitting this weekend's homework.__

This project structure includes:

- A `package.json` file which was made after the project was initialized and which will serve many purposes, one of which is to save our required and dev dependencies
- A `src` folder which contains the unoptimized source code for the project
- Handlebars template files and a directory structure within `src/views/` to organize them
- A `public/` folder which keeps static assets organized. The Express application will be configured to serve all static assets from this folder.
- A `gulpfile.js` which defines all of your project's development, build, and deploy tasks. In other words, all of your Gulp tasks get defined here
- An Editorconfig file will set your text editor's tab spacing and other settings that helps keep text settings in sync between different computers and text editors
- Your `.gitignore` file should, at the very least, include `node_modules/`. You never, *ever* track dependencies within any git repository. This applies to all programming languages. Your project dependencies should always stay local and should never make it into any git repository. This is because other users of your project may need to compile certain dependencies in a way that is specific to their system. Each person who clones your project should be running `npm install` to get the project dependencies individually.
- Your main server file is within `src/index.js`. This file requires your application's dependencies, configures the server, defines your routes, and then starts the server

Any other files or folders I haven't mentioned are still important but are self-explanatory.

## Set Up Development, Build, and Deploy Tasks (Gulp Tasks)

Gulp, the task runner we are using, is made for defining development, build, and deploy tasks. What kind of tasks are those?

- __Development tasks__ are those tasks that you need to run while developing the application. These include running a local server, transpiling LESS files, linting JavaScript, etc.
- __Build tasks__ are tasks that are meant to create optimized versions of files that speed the delivery of assets and make your site run faster. Examples of this include concatenating and minifying your front-end JavaScript and minifying your CSS. You only need to minify client-side/front-end assets. Your back-end files have no effect on download times or site speed in general.
- __Deploy tasks__ are ones that automate publishing of your web application live online

### Setting up a Gulpfile

A `gulpfile.js` is set up to define your Gulp tasks. A Gulpfile should be put in your project's root and called `gulpfile.js`.

 `cd` into your project's root folder and install the Gulp local library by running `npm install gulp --save-dev`.


The basic structure of a Gulpfile is as follows:

```js
// Require deps
var gulp = require('gulp'),
    less = require('gulp-;ess');
// Additional Gulp plugins can be required here

// Define a task to transpile LESS to CSS
gulp.task('less', function() {
  gulp.src('./src/public/less/style.less') // 1. Get file contents
    .pipe(less())                          // 2. Pipe contents of style.less into the `less` plugin
    .pipe(gulp.dest('./src/public/css'));  // 3. Pipe the output of the `less` plugin function to a final destination file
});

// Gulp example task using plain old JS code
gulp.task('example', function() {
  console.log('The example task has run!');
});


// Watch task - runs other tasks when files change
gulp.task('watch', function() {
  gulp.watch(['./src/public/less/**/*/.less'], ['less']);
  // Other files can be watched by Gulp and tasks run bsed on
  // when they change. For example, you can lint and minify JS files
  // when files in ./src/public/js/ change. An unlimited amount
  // of 'gulp.watch(...)' tasks can be defined here
});

// Define a default task
gulp.task('default', ['watch', 'example']);
```

#### Gulp methods

Gulp has a handful of API methods that'll help you transform files. These are:

- `.task(name, [callback, array of tasks])` - This method takes 2 arguments. The first is the name of the task as a string. The second argument can be a callback function or an array of task names to run when the task is invoked.
- `.src([array of files to read])` - This method takes a single file or folder path or an array of file/folder paths (including path patterns) and will return the contents of those files
- `.pipe([Function])` - The pipe pethod taskes the output from the previous method it was chained to and passes it to the function that is passed into it. For example `something.pipe(less())` takes the result of `something` and passes it to the `less()` function within it. It will then output the result so you can pipe it to another mehod using `.pipe` again
- `.dest([Path])` -- This method takes a file path and will write the output from the previous command into the file path you pass to it. Use it along with `.pipe` for   best effect

## Set up Express

Now that you've set up all the Gulp tasks you *know for sure* you're going to be using, it's time to start coding your Express app. 

The first step in coding an Express app is installing the depndencies you *know you need* to run an Express app. Express comes with a great API on its own that allows you to set up routes paired with methods. Next, install the required packages. You'll want:

- `express`  - The web framework
- `express-handlebars`  - A library that sllows use to use Handlebars                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       
