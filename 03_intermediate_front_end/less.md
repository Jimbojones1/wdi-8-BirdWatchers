# LESS

[LESS](http://lesscss.com) is a superset of CSS and a CSS transpiler. It takes a special CSS syntax and turns it into regular CSS.

## Installation and usage

Run `npm install -g less` to install the LESS transpiler globally. This means that the package will be installed as a runnable command line program that can be accessed anywhere on your system. Installing Node packages globally (using the `-g` flag) allows them to be used from any directory on your system inn the same way commands like `cd`, `ls`, or `git` can be accessedd globally.

## Transpiling LESS to CSS

In the LESS CLI (command line interface) there are a number of features and options you can utilize. You'll only use one main feature of the program: transpiling LESS to CSS. To do this, you run this command:

__Transpiling overview__

```
lessc <path to less file> <path to output file>
```

The LESS program command's name is `lessc` (*note the "c" at the end of the command*). It's named `lessc` so that it does not interfere with the `less` program which is used to read files on the command line. Please __do not confuse `lessc` (the LESS transpiler) with `less` (the file reading program)__.

__Example of using the LESS transpiler__

Suppose you're in the root of your repository and you have a `less/` folder, `css/` folder, and other files. The folder structure may look like this (some files left out for the sake of this example):

```
my_project
  |
  --css/
  |  |
  |  -- style.css
  |
  -- less/
    |
    -- style.less
    |
    -- colors.less
    |
    -- type.less
    |
    -- grid.less
```

In this example you have a `less/` directory with 4 files. One for color variables, one for typographic styles, one for the grid system, and finally, we have the `style.less` file. By convention, your `style.less` file will *only* be used to import styles from the other files. One reason we use LESS to begin with is so that we can modularize our code and transpile it into one file that has all of the files put together in order.

Your `style.less` file will likely look something like this:

```less
// Main stylesheet
// ---------------
// When importing, you do not need
// to specify the file extension - only the path.
// LESS knows that you're importing other .less files
// by default so that's why the extension is optional.

@import 'colors'; // Defines all of our color variables - all files imported
                  // after this will have access to them
@import 'type';   // Import typography styles
@import 'grid';   // Iimport the grid system
```

The order of your `@import` statements is important because variables declared in one `.less` file will only be available to expressions within that file *and* the files imported after it. So in our example any file imported after `colors.less` will be able to use the `colors.less` variables.

__Running the transpiler__

Now, finally, to turn your `style.less` file into a fully functional `style.css` file full of transformed CSS you run this command using the `lessc` command line tool:

```
lessc less/style.less css/style.css
```

If your current path was the root of the project we talked about above then what this command is saying is "read the file located at less/style.less and transform it into a CSS file at the path css/style.css". Simple!

## LESS Features

### Variables

You can use variables to hold a value and reuse it in other parts of the file.

```less
@heading-color: #505050;
@body-color: #272727;

h1, h2, h3, h4, h5, h6 {
  color: @heading-color;
}

p {
  color: @body-color;
}
```

### Nesting

You can nest selectors within other selectors. This makes writing CSS faster and more efficient.

With HTML like this:

```html
<ul>
  <li>My</li>
  <li>list</li>
</ul>
```

```less
ul {
  background: #505050;
  list-style: none;

  li {
    color: #f7f7f7;
    display: inline;
  }
}
```

### Mixins

A mixin is sort of like a function. It can take arguments and whatever the contents of the mixin are, they will be transferred into the CSS selector that you add it to.

```less
// Creates a mixin that changes background colors
background-mixin(@color) {
  background-color: @color;
}

// Now we can use this mixin in any other class definition
.my-element {
  .background-mixin(blue);
}
```

The above would turn into this CSS:

```css
.my-element {
  background-color: blue;
}
```

### Imports

You can import files and turn multiple LESS files into a single one. This is useful for modularizing your LESS. A common practice is to have a `style.less` file which imports all the style rules from external LESS files.

```less
@import 'variables';
@import 'colors';
@import 'typography';
@import 'grid';
```
