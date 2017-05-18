# Gulp from Scratch

> Creating a Gulp workflow from scratch

## What is Gulp?

Gulp is a task runner for Node.js. Most languages have task runners, sometimes multiple options. Node.js has two main competing task runners - Grunt and [Gulp](https://github.com/gulpjs/gulp/blob/master/docs/getting-started.md). During this course we're going to choose to focus on Gulp because it allows us to get familiar with writing Node.js style JavaScript code. Grunt is a perfectly good choice but it follows a different philosophy. Feel free to check out Grunt once you feel comfortable with task runners.

*Note: [Gulp's getting started guide is a great place to start](https://github.com/gulpjs/gulp/blob/master/docs/getting-started.md) learning how to use Gulp.*

### What is a task runner?

It's common to build projects that grow in complexity. At first you might have simple static files that require you to just transpile some LESS into CSS but soon enough you end up having to run a local web server, check it for style or logic errors, transpile LESS into CSS, and minify front-end JavaScript.

Running each of these tasks on their own can become tedious. A task runner helps because it allows you to define and then combine one or more tasks together.

A task runner can run tasks manually or automatically. When you worked with LESS, you needed to run the `lessc` command each time you made a change to your LESS files. Now imagine that you had to run multiple tasks each time a LESS file or a JavaScript file changed. That would be a pain.

#### Watch tasks

When you need to run commands when certain kinds of files change, a "watch" task comes in handy. Gulp has a `watch` method which will watch a directory for changes to a file and then run tasks you've defined.

## How to use it

To use Gulp your Node.js project must be set up as a package by using the `npm init` command in the project's root folder. Once you have initialized a new Node.js project, also known as an "npm package" or Node module, you can install the required libraries and define Gulp tasks in a special file called a `gulpfile`.

__Setting up Gulp tasks__

1. Be sure that your project is a Node module by running `npm init` in your project's root folder
2. Now install Gulp. You must have the Gulp command line utility installed globally and a separate library installed locally as a project dependency. You can install the Gulp CLI globally by running `npm install -g gulp-cli`.
3. Install Gulp locally by running `npm install gulp --save-dev`
4. Create a new Gulpfile by running `touch gulpfile.js`
5. Now you can install any additional libraries and utilities (called plugins) that work with Gulp like a LESS transpiler or JavaScript minifier

### A basic Gulpfile

A basic Gulpfile looks like this:

```js
var gulp = require('gulp');

gulp.task('default', function() {
  // your default task is a special task.
  // it gets run whenever you run "gulp" with
  // no other arguments on the command line.
  console.log('This example task does nothing useful yet.');
});
```

This task would print some text to the console whenever you ran `gulp` in your terminal. You can define additional *named* tasks which you can run by entering `gulp my_task_name` on the command line.

### A Workflow

Gulp tasks defined or run in isolation can be useful but the same problems that arise from having to run programs like LESS transpilers on their own can plague Gulp (or any task runner). The main problem is the tedious nature of running them. Even when you combine tasks, if you have to run them manually each time a certain file or type of file is changed it becomes tedious and time consuming.

A Gulp workflow is a set of tasks that run in order and do one important thing. For example, you may have a development version of a project that includes a test suite, uncompressed/non-minified files, and other files that may need processing to be optimized for your final audience.

A set of gulp tasks - one Gulp task that runs one or more additional Gulp tasks - may be used to prepare a project for deployment. It may run the following sequence of tasks:


- Transpile LESS into CSS
- Minify your CSS files so they download faster when the client visits your site
- Minify your front-end JavaScript files for the same reasons you minify your CSS
- Run a linter on your JavaScript files to catch any coding mistakes or bad code style before the program runs

## Conclusion

Now that you know how to set up a Gulp workflow it's time to learn how to use Gulp's API and plugins to write some useful tasks and set up one or more workflows.


