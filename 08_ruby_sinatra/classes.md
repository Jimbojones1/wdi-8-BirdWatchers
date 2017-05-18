# Classes in Depth

Classes are how we create Objects. Objects are used by programs to do work. A program knows what goes into an object, what an object can do, and what an object can return to it but the program doesn't know how the object does it *because it doesn't need to*!


## The Non-Programmer's Guide to Understanding Object Oriented Programming

Let's suppose I am a "Human" program. I have normal things to do like walk the dog, take a bath, feed the fish, etc. As a program, I call on other, more specialized, objects to do work for me. These objects are used by me all the time but I don't know that much about them. On Saturday I need to get my laundry done so I call my friend Sarah over, hand her a bag of my dirty clothes, and tell her that I need my laundry done.

Sarah goes to the laundromat, puts in the correct number of quarters, separates whites from colors, then folds my clean laundry nicely. She comes back to my place a couple of hours later and hands me back clean clothes.

In this story I was a program and Sarah was an object. Specifically, she was an object of the "Laundry Person" class. As an object she had attributes and methods. I had no knowledge of where the laundromat was, how many quarters were required to dry clothes, how to separate my colored and white clothes,  or how to fold my clothes. But Sarah did know all that stuff. She had quarters and a knowledge of where the laundromat is (attributes) and she had the ability to clean and fold those clothes (methods).

In order to interact with an object you don't need to know how the object works. All one needs to use an object is:

1. Create a new instance of a class (this creates the object)
2. Know what arguments the class constructor or other methods take
3. Know what to expect for return values

## Creating Objects

To create Objects we first make classes. Objects are individual instances of classes. This is done using the `.new` method of a class.

### Accessors

Accessors are how you read and write the value of object *attributes*. Sometimes you only want a program to be able to read attributes. Other times you may want object attributes to be writable only. And still other times you may want a class attribute to be both read and written to. Because it's common for you to simply want to set or get an object's attributes without doing any other work or changing the object in any other way, Ruby provides the `attr_*` shortcut methods. These methods will create getters and/or setters for you automatically.

* **Accessors**: create getters and setters for instance variables
* **`attr_reader`** —> creates getter
* **`attr_writer`** —> creates setter
* **`attr_accessor`** —> creates both getter & setter
* __`def my_getter_or_setter() ... end` -> Manually create a getter or setter

You can have a class that takes arguments in it's constructor but without any `attr_` methods you cannot read or update those attributes on any instance of your class. Basically, without attribute readers or writers, once you instantiate a class it's properties are set in stone. You might want to do this sometimes but in 99.99% of cases you'll want each of your class' attributes to either be readable or writable.

__Example__

In this example we use each of the 4 styles of creating accessors. We will be using:

- `atr_reader` to create a getter method
- `attr_writer` to create a setter method
- `attr_accessor` to create both a getter and setter automatically
- Manually create a getter and setter method

__Pro tip:__ Unless you need to do some work on an object's value before setting it, it's best to use the `attr_` methods rather than manually create getters and setters. An example of when you would want to manually write getter/setter methods would be if you needed to filter out special characters from a string, check the length of the value (for a Login class maybe), or maybe just mess with users and give them unexpected output.

```ruby
##
# Car
# ---
# Creates a new instance of a car with these attributes:
#
# - `brand` [String] <optional> - Sets brand of car (optional arguments)
# - `rims` [Fixnum, Float] - Number that represents the size of the car's rims in inches
class Car
  attr_reader :rims     # Auto-create a getter for @rims
  attr_writer :rims     # Auto-create a setter for @rims
  attr_accessor :color  # Auto-create both a getter AND setter for @color

  # Constructor - The `.new` function run when creating new instance of an object of this class
  def initialize(brand='Honda', rims, color)
    @brand = brand
    @rims  = rims
    @color = color
  end

  # Getter method for brand attribute
  def brand
    @brand
  end

  # Setter for the brand attribute
  def brand=(brand)
    @brand = brand
  end

  # Defining a public method on a class - will turn the instance of the class into a string for clean user output
  def to_s
    "I am a #{@brand} car that is #{@color}" # Note that I don't need to `return` from methods unless I want to exit them early
  end
end

# Our class has ended and now we can use it to create a program:
# --------------------------------------------------------------
# This program will create a 2008 VW Jetta and print out it's attributes
gordon_gecko = Car.new 'Volkswagen Jetta', 17, 'Silver-gray' # I named my own car Gordon Gecko because I was obsessed with getting rich when I bought it

puts gordon_gecko.to_s # Run the program to see its output. Also try these variations:

puts gordon_gecko
p gordon_gecko
```


## Variables

Variables are named placeholders for storing values. They work the same way they do in JavaScript except you do not need to use the `var` keyword to define a variable the first time you create or assign a value to it.

There are four different types of variables you'll be working with in Ruby:

* **local** —> lives within the space it is declared in (local scope)
* **$global** —> can be accessed from anywhere (global scope - like most JavaScript variables)
* **@instance** —> can be accessed by all methods in INSTANCE of that class
* **@@class** —> can be accessed by class & all instances of that class

## Methods

Methods are functions in a class. They belong to the class they're defined in.

__Example:__

```ruby
class Car
  attr_accessor :started

  # Constructor
  # -----------
  # This simple constructor just starts
  # an instance of a car (or you can instantiate
  # a new car with the engine turned off)
  def initialize(started)
    @started = started || false
  end

  # This simple method will flip a `@started` instance
  # variable from true (on) to false (off) each time the method
  # is called.
  def turn_engine
    if @started
      @started = false
    else
      @started = true
    end
  end

  # Car#beep
  # --------
  # Like honk method but it's an instance method
  def beep
    "Beep beeo"
  end

  # Car#honk
  # --------
  # Honks the car's horn. This is a class
  # level method. It can be used without creating
  # a new instance of the Car class
  def self.honk
    "HOOOOONNNNNNKKKKKKKK!"
  end
end
```

* Class methods (can be called on a class without creating new instances of it)
* Instance methods (can only be called on instance of class)

__Examples:__

```ruby
# Assuming we have the Car class we defined above available here...

# Here's how we use a class method
puts Car.honk #=> "HOOOOONNNNNNKKKKKKKK!"

# How to use instance methods:
honda = Car.new()
```

