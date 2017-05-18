## React-gulp

To convert our react into readable javascript code we need to install a 
ton of node modules.   

lets install
1. npm install babel --save-dev
2. npm install babelify --save-dev
3. npm install vinyl-source-stream --save-dev 
4. npm install react react-dom --save-dev
5. npm install babel-preset-react --save-dev
6. npm install babel-preset-es2015 --save-dev
7. npm install browserfiy --save-dev

## Then lets go to our gulp file and require the dependencies we need on top
```
var browserify = require('browserify'),
    babelify   = require('babelify'),
    source     = require('vinyl-source-stream');

```

Now we required our dependencies now lets write our task

```
  gulp.task('react', function(){
  return browserify('./clientReact/app.js')
          .transform('babelify', {presets: ["react", "es2015"]})
          .bundle()
          .pipe(source('build.js'))
          .pipe(gulp.dest('./src/public/js'))
})
```

We our naming our task `'react'` and we are using browserify to take the react code
located in the folder clientReact/app.js and transforming it using babelify with the 
two presets `['react', 'es2015]`, you are then using the `source` method to name the new 
file we our creating that contains our converted react code in the app.js file and we our naming
it `build.js`.  We our then sending it to our public/js folder.


## Now we need to add React to our watch task 

```
gulp.task('watch', function() {
  gulp.watch(['./src/public/less/**/*.less'], ['less']);
  gulp.watch(['./clientReact/*.js'], ['react'])
});

```

This will listen for a file to be saved, then to run the react command.
As you probably noticed when gulp crashes we have to restart gulp and 
resave our js file. Lets be lazy and not do that anymore by augmenting our
`default task` this tells gulp when it starts to run the watch command that listens
for any file changes, and run the react task.

```

gulp.task('default', ['watch', 'react']);

```


## Now we need to make sure our app.js is setup properly

our file should look like this

```
var React     = require('react');
var ReactDOM  = require('react-dom');

```

now run gulp, is it working ? Did you install all the dependencies, Did you link
up the build.js to the view that is using it so you can see your results?

