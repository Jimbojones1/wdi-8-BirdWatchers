# Advanced Arrays and Looping in JavaScript

> Today we covered array methods and loops

## Arrays

Arrays are lists of values. An array can contain *any* type of value including other arrays. In fact you can nest arrays within arrays within arrays infinitely.

### Defining a new array

You can create new arrays that are empty or have content by default. Both of these examples are valid ways to create a new array:

```js
var emptyArray = []; // A new, empty array
var myArray    = ['Horses', 'Cows', 'Pigs', 'Sheep']; // Array with items in it
```

### Methods on the Array Object

The Array object (in other words, anything that is an array) has a number of built-in methods you can use to work with it.

#### `length`

The `Array.length` property will give you the number of values stored inside of an array. This is technically a __property__ of an array (it describes it rather than executing functions - it is a plain value).

__Example:__

```js
// Try running this in the Node REPL
var myArray = ['Horses', 'Cows', 'Pigs', 'Sheep'];
myArray.length //=> Returns '4'
```

### `map`

The `map` method is related to loops but has a specific purpose: to manipulate each value in an array and return the results as a new array. __This method returns a new copy of the changed array, it does not affect the original array.__

__Example__

In this example we lower-case all of the values in the array and create a new, all lower-cased animals array.

```js
var animals = ['Horses', 'Cows', 'Pigs', 'Sheep'];

var lowerCaseAnimals = animals.map(function(value, index) {
  return value.toLowerCase(); // toLowerCase() is a string method native to JavaScript
});

console.log(animals);
console.log(lowerCaseAnimals);

// Run this in the Node.js REPL to see the results
```

### `filter`

This method keeps or removes values from an array based on a conditional expression you specify. The `filter` method works in a similar way to `map` in that it takes a callback with arguments that are the current value and its index in the array. The similarities end there. The callback you provide to `filter` __MUST__ return a boolean value. If the expression you use in the callback function returns `true`, the value is kept in the array, otherwise the value is removed from the array if your expression is `false`. This method returns a new copy of an array, it does not change the original array in place.

__Example__

Here we're going to create a new array of only even numbers from another array of mixed numbers. We'll use filter to only keep evens.

```js
var numbers = [1, 2, 3, 4, 5, 6];

// Because filter does not change the original array we have to store it's return 
// value in another variable OR we can redefine the original numbers array
var evens = numbers.filter(function(value, index) {
  return value % 2 === 0; // This says if value divided by 2 has no remainder then return true, otherwise false
});

console.log(numbers, evens);
// Try running this in the Node REPL and see what you get
```

## Loops

Arrays are a data type you will want to loop over at some point. The reason loops exist is so that you can easily retrieve or change the values of an array using a block of code instead of having to individually grab each array value by it's index. And what if you don't know how many items are in the array? In these cases a loop is a great way to work on all the values in an array no matter what it contains or how long or short it may be.

Most loops use "iterators". These are variables that contain a number and are used to count how many times the loop has run. Iterators are commonly started at 0 or 1. The common practice for loops is to name their iterators `i` (as in `var i = 0;`).

Incrementing the iterator is essential to making sure some loop types run. We use the increment operator for this purpose (`i++`).

Most loops require you to supply an expression that evaluates to a boolean value - either `true` or `false`. If you provide the array with expressions that evaluate to "truthy" or "falsy" values instead of the literal `true` or `false` keywords then you risk creating an infinite loop.

#### The `while` loop

This is the least common loop type. You will rarely see it but know it exists. It works by taking a boolean expression and running until the expression is no longer `true`. You must manually set and increment an "iterator". An iterator is created in the global scope and then incremented in the body of the loop. This incrementer is often used in the expression part of the loop to cause it to evaluate to `true` or `false`.

__Example__

This example basically says "while `i` is less than or equal to the length of the animal array minus one, run the code within the block I give you".

```js
// This is our array
var animals = ['Horses', 'Cows', 'Pigs', 'Sheep'];

var i = 0; // This is our iterator (it is in the global scope)
while (i <= animals.length - 1) { // We subtract 1 from the animal var's length to account for array indexes starting at 0
  var currentAnimal = animals[i]; // The incrementer is used to access the array at an index number
  console.log('The current animal is: ' + currentAnimal); // Outputs the current animal to the screen

  i++; // We MUST increment 'i' otherwise we will always be accessing the same index in the array
}
```

#### The `for` loop

The `for` loop improves on the `while` loop. The `for` loop forces you to remember to create an iterator, expression, and incrementer. Most importantly, it keeps it's iterator in a local scope so you don't need to worry about variable name conflicts.


__Example__

```js
var animals = ['Horses', 'Cows', 'Pigs', 'Sheep'];

for(var i = 0; i <= animals.length - 1; i++) { // 'for' forces you to define an iterator, expression, and increment all in one line
  var currentAnimal = animals[i];
  console.log('The current animal is ' + currentAnimal + ' at index ' + i);
}

// NOTICE that we didn't use i++ at the end of the loop.
// We don't have to. for loops do that for us.
```

#### The `forEach` loop

`forEach` is a method on the array object you can use to loop over an array. __Use this array always__. This is *the best and easiest loop*. You will see the other loop types used by others so it's important you recognize them but you usually won't use the other loops unless you have a good, specific reason to. Otherwise the `forEach` loop should be the loop you use most often.

Much like `map` and `filter`, the `forEach` method takes a callback and it's arguments are the current value and array index number. The difference is that you __do not have to return anything__ from a `forEach` loop. You can simply do some work without having to return any values. Using a `return` statement inside of a `forEach` loop will cause you to prematurely stop the loop. You may want to do this sometimes but usually you won't.

__Example__

In this example we're going to output the values of an array just like we have for the other loop types except this one will be clean and short.

```js
var animals = ['Horses', 'Cows', 'Pigs', 'Sheep'];

animals.forEach(function(animal, i) {
  console.log('The current animal is ' + animal + '. It has an index number of ' + i);
});

// Notice that there's no return statement here.
```

#### The `for in` loop

This is a loop that can be run on arrays but is usually reserved for objects. The for-in loop will loop over all of the keys inside of an object and then allow you to get their corresponding value by using the object bracket syntax.

__Example__

Here we will create an object that describes a person and then loop over that person object's keys and get the values associated with it. It will log the keys and values to the console.

```js
var person = {
  height: 'tall',
  sex: 'female',
  hairColor: 'brown',
  eyeColor: 'blue'
};

for (var prop in person) {
  var value = person[prop];
  console.log('This person has a ' + prop + ' of ' + value);
}
```

Try running this in the Node.js REPL.











