# Functions and Scope in JavaScript

Functions are a data type that take input and output values based on their input.

Functions let you break larger projects up into smaller pieces. They also help you to not repeat yourself. You define a function once and use it in many different places.

## Arguments

Functions can take one or more arguments. Each argument will change the output of the function when it returns.

## Example

This example function just adds two numbers together and returns the result.

```js
function addNumbers(a, b) {
  return a + b;
}
```

Once a function is defined you need to call it. To call a named function you just invoke its name with parentheses, filling in any arguments it might require like this:

```js
// Call addNumbers function
var result = addNumbers(2, 2);
```

The above will store the result of `addNumbers` to the variable `result`. It is common to store the return values of functions in a variable so you don't have to run the function each time you need to get it's return value.

## Functions Exercise

__The Fortune Teller Game__

Write a function named `tellFortune` that:

- Takes 4 arguments: number of children, partner's name, geographic location, job title.
- Tutputs your fortune to the screen like so: "You will be a X in Y, and married to Z with N kids."
- Call that function 3 times with 3 different values for the arguments.


