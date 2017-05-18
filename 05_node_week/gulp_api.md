# The Gulp API

> Gulp borrows the idea of "piping" data from one function to another to run its tasks

*NOTE: For the sake of example, we're going to assume we've created a `gulpfile.js` and set up the basic boilerplate. Assume for the rest of these notes that we are writing the code within a file that is set up like this:

```js
var gulp = require('gulp');

// Your Gulp tasks and workflow
// are defined here. Assume all the
// examples are being added in this 
// space.

// Assume a default task is defined last
gulp.task('default', function() {
  // Default task body defined here...
});
```

## The `task`, `src`, `pipe`, and `dest` methods

Gulp has a method called `task` that takes 2 arguments: the task name as a string and a callback function that runs the task itself.

__Example__

```js
var less = require('gulp-less'); // Require a plugin that makes transpiling less easier

// less
// ----
// A task to transpile less files.
// Takes the main `style.less` file and
// transforms it into the main `style.css` file.
//
// Usage: Run `gulp less`
gulp.task('less', function() {
  gulp.src('./public/less/style.less')
    .pipe(less())
    .pipe(gulp.dest('./public/css/style.css'));
});
```

This task takes a file path and passes it to `gulp.src()`. Gulp's `src` method takes one argument: either a single string representing the path to a source file (in this case a LESS file). It then uses Gulp's `.pipe` method to take the output of the `src` method and pass it to any arbitrary function - in this case a `less()` function that transforms LESS into CSS. We then use `pipe()` once again to send the output of the `less()` function to Gulp's `.dest` method. The `dest` method takes a single argument: the destination path to a final output file that will be written.

So, all together we created a task that takes a LESS file as input at the beginning and outputs it as a CSS file in a different location at the end. The native `gulp` methods we use for this are:

- `gulp.task()` - Gulp method that defines a task
- `gulp.src()` - The method that takes a source path
- `gulp.pipe()` - The method that passes function output from one function to another. These can be gulp's own methods or functions exposed by gulp plugins like the `less()` function which we imported using a Gulp plugin
- `gulp.dest()` - This native `gulp` method takes the output of the previous method and writes it to a file. This is usually the file's final output or destination.

## How Gulp Works

> Or: the philosophy of the Gulp task runner

We talked before about there being alternative task runners for Node.js such as Grunt. Grunt uses a system of plugins and configuration objects to create tasks. Grunt tasks are pretty much pre-defined and all you need to do is pass it an object that defines the source file, destination file, and some other options depending on the Grunt plugin used for the task. Grunt's philosophy is to make task definitions easy by asking you to configure simple inputs and outputs and let the rest be handled behind the scenes.

Gulp on the other hand takes a different approach. It gives you a lot of freedom to define tasks to be written in whichever way you like. Gulp does have plugins that make this easier but for the most part all Gulp tasks are made up of plain Node.js code. Gulp lets you write plain JavaScript code right within your tasks while other task runners restrict you to only using their own predefined methods and configuration blocks.

### Anatomy of a Gulp Task

1. You define a task name with `.task()`
2. Define the input file(s) using `.src()`
3. You may send the source file's output to another method or function by piping it in a chain using `.pipe()`
4. The final output file is then created by passing the output to Gulp's built-in `.dest()` method

## Creating a workflow

A workflow is a set of tasks that run in order. To create a workflow you must first define each individual task. So let's suppose you created tasks for `less`, `jshint` (for pre-checking JS code for errors), and `uglify` (for minifying JavaScript) individually and you'd like to run these tasks in order before you deploy your site live. If you wanted to run this task, you'd create a workflow like this:

__Example of a Gulp Workflow__

Creating workflow tasks is easy! You simply start by defining a named task using the `.task()` method but instead of passing a callback function as a second argument you supply it an array of named tasks. Gulp will then run each individual task in order and you have a workflow!

```js
// First you define the tasks you'll need in your workflow
gulp.task('less', function() {
  // task body goes here...
  // LESS turns into CSS at the end of it
});

gulp.task('jshint', function() {
  // task body here...
  // you would run a JS linter here
  // More info on what a linter is: http://www.javascriptlint.com
});

gulp.task('minify', function() {
  // task body goes here...
  // code to minify one or more JS
  // files goes here..
})

// Workflow task - THIS IS THE IMPORTANT PIECE
gulp.task('optimize', ['less', 'jshint', 'minify']);
```

To run the workflow you simply run `gulp optimize` from your project's root folder.

## Watch tasks

A watch task is a task that watches files for changes and then runs a task when a file changes.

__Example__

In this example we run a local web server and watch for changes to LESS files and automatically convert them into CSS files without having to manually run any gulp tasks. Let's assume we've already created the tasks needed to compile the LESS files, optimize our JavaScript (using linting and minification), and run a local server all at once. Let's suppose we've called those tasks `less`, `minify`, `jshint`,  and `server`.

```js
var gls = require('gulp-live-server');

// Server task
// -----------
// Starts a local web server at http://localhost:9000
// Run a local server
gulp.task('server', function() {
  var server = gls('./server/app.js');
  server.start();

  // Reload the server on changes to back-end file changes
  gulp.watch(['./gulpfile.js', './server/app.js', './server/{config,controllers,middleware,models}/**/*.js'], function() {
    server.start.bind(server)()
  });
});

// Watch task
gulp.task('watch', function() {
  gulp.watch(['./public/less/**/*.less'], ['less']);
  gulp.watch(['./public/js/**/*.js', './server/{controllers,models,lib}/**/*.js'], ['jshint', 'minify']);
});

// Best practice dictates that we use the default task to run our watch tasks
gulp.task('default', ['watch', 'server']);
```

In the setup above, our default task runs the watch task and then the server task in order. This creates a local web server which we can access at the location we specify (http://localhost:9000 in this case). Now all of our LESS files, front- and back-end JS files are being watched for changes, and when any of them change, the correct Gulp task gets run.

For example, if we changed *any* LESS files then the `style.less` file would be run through the `less` task and turned into a finished `style.css` file in the CSS folder. Same goes for all of our JavaScript files. Both back and front-end JS files will be run through the `jshint` and `minify` tasks when you change any of them.

All of this happens without you having to take any action except for running the `gulp` default task one single time. From that point on all you need to do is work on your project nad when files change, the correct task runs without you having to take any action in the terminal.

To quit watching files you simply run `Ctrl + C` in your terminal and the Gulp tasks will quit.

## Conclusion

The Gulp API is simple enough. All together the steps are:

1. Define a task
  - Define a source file to start with
  - Pipe its contents to one or more functions using Gulp's piping features
  - Use Gulp's `dest` method to send output to a particular location
  - Use `watch` where appropriate to watch files for changes and run tasks each time that file type is changed
2. Run the task
3. Work on your project without worrying about what's happening in the terminal

Gulp seems very complex when you first start using it but once you understand the source, pipe, dest, watch workflow you can easily define custom tasks that'll do whatever you want.
