# Ruby Basics

> Basic data types, blocks, and looping

## The basics

In Ruby thre *are* curly braces and there *are* semicolons. It's just that you never see them because they're optional and the creators or Ruby specifically intended for the language to be free of brackets and semicolons. Sticking to conventions will make you a good programmer so while you can technically create blocks with curly braces and end expressions using semicolons __refrain from doing so at all times__ unless you have a good reason to use them. There are good reasons to use them but they are few and far between. You'll likely not find a good use for these things until you've programmed in Ruby for at least 2 years.

Ruby relies on indentation and its `end` keyword to delineate the end of a block of code. Here's an example:

```ruby
if true
  puts "It was true"
end
```

## Strings, Floats, Integers, and Doubles

These are data types we are all familiar with and need no explanation. Because you know them so well from using JavaScript we're going to skip straight to the examples. Please note that Node.js has the `Number` data type while Ruby has more nuanced `Integer`, `Float`, and `Double` data types which are subtypes of what you'd think of as a number.

```ruby
name = 'Bill Patrianakos' # A string

# Number data types...
my_int    = 100       # An integer
my_float  = 100.14324 # A floating point number
my_double = 100.25    # A floating point integer with double precision (useful for working with money)
```

## Arrays

An array is a list of values separated, by default, by a comma. Ruby arrays are created, treated, and used almost identically to JavaScript arrays. There are ways to use different separators and tell Ruby that your array will contain only strings so you don't need to use double quotes. You should definitely look into that. For now we'll cover the basics.

### Pushing and popping

See the Ruby docs. Array values can be `pushed`, `pull`ed, `shift`ed, and `unshift`ed just like JavaScript arrays. The methods work exactly the same except instead of using a callback we pass it a block.

### Filtering

Filtering arrays is done using the `select` method of the array. Here's an example of getting all of the even numbers from an array:

```ruby
numbers = [1, 2, 3, 4, 5, 6]

evens = numbers.select do |n|
  n % 2 == 0
end

puts evens #=> Returns [2, 4, 6]
```

__You might have noticed that there are *no return statements*__ in the code sample above. This is because the last expression that evaluates in a Ruby file is automatically returned. __There is no need for a return statement in Ruby__... but you can still use it if you want to be a Luddite and write bad code.

### Mapping

Mapping works the same way in Ruby as it does in JavaScript. You change each value in a Ruby array and keep the original array intact while returning a new set of changed values.

```ruby
names = ['bill', 'jim', 'teddy']

names.map! do |name|
  name.capitalize
end

puts names #=> [Bill, Jim, Teddy]
```

__Did you notice the `!` at the end of the `map` method? That's called a "bang method".__ Some methods have both regular and bang versions of their method names. The regular `.map` method returns a brand new array with changed values. The `.map!` (bang version) method does the same thing but it changes the variable value in place. This means that you do not need to create a brand new array to hold the changed values. The array is changed in place.

## Hashes

Hashes in Ruby will look very similar to JavaScript objects (POJOS). A hash looks like this:

```ruby
student = {
  name: 'Bill',
  age: 29,
  # More goes here...
}
```

The above is the newest hash syntax in Ruby. Sometimes (like with multi-word or proprties with special characters in them), you may need to change the syntax you use. Here is the original, alternate syntax and a use-case for it:

```ruby
headers = {
  'Content-Type' => 'text/html',
  # More here
}

student = {
  name => 'Bill',
  age  => 29,
  # etc...
}

### Iterating over hashes

Just like arrays, you can loop over hashes as well. In Ruby, passing a block to a hash's .each method lets you get both the attribute name *and* the value associated with it. No more having to bend over backwards to figure out the value of a particular key in hash like when you used JavaScript.

__Example:__

```ruby
student = {
  name: 'Bill',
  age: 29,
  height: '6ft 0in',
  favorite_color: 'Green'
}

student.each do |key, val|
  puts "#{key} is #{val}"
end
```

Try running this yourself in `irb`.

#### Did you know there's a shorter way?

For all blocks, you can turn them into one-liners. If your block has only a single statement in it, you can turn it into a one-liner. For example, the above example would be written like this:

```ruby
student.each do { |key, val| puts "#{key} is #{val}" }
```

# Homework

Your homework can be found in [the homework repository](https://github.com/ga-chicago/wdi5-homework) for week 8. As always, create a new folder named after yourself in this week and day's homework folder.
