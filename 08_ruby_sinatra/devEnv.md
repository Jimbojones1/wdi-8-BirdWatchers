4.1 Setting Up a Development Environment

Before we get started, we need to all be on the same page! That means we need to have the same version of Ruby as well as the same tools. Let's do that!

1.  Install rbenv, a Ruby environment manager: brew install rbenv
2.  Now, have rbenv install Ruby version 2.2.0: rbenv install 2.2.0
Choose the global version of Ruby (for your entire Mac) to version 2.2.0: rbenv global 2.2.0
Finally, install pry - the Ruby REPL console that we'll use: gem install pry
PS: gems are Ruby applications. You can install them using gem install gem_name. For a complete listing: https://rubygems.org/






1. How many hours are in a year.
2.  How many minutes are in a decade?
3.  How many seconds old are you?




3.0 / 2
3 / 2.0
4 ** 2.0
4.1 % 2
Is the result a float or an integer?


Methods are a way of “doing something with an object”. E.g. in Ruby, numbers have two methods that allow you to check whether the number is odd or even.
Look through the documentation for integer numbers (called Fixnum) and find the methods that tell if a number is odd or even.



Skim through the documentation for strings in the Ruby documentation, and look for a method that prepends one string to another string.
Using that method prepend the string "Learning " to the string "Ruby"

Skim through the documentation for strings in the Ruby documentation, and look for a method that removes characters from a string.
Using that method turn the string "Learning Ruby" into the string "Lrnng Rb".

Find out how to convert the string "1.23" into the number 1.23.
You can either, again, skim the documentation page for strings, or google for “ruby convert string to number”.
Then also find out what method can be used to turn the string "1" into the number 1 (remember floats and integers are different kinds of numbers).

There is a method that allows to justify a string, and padding it with another string.
Find that method and use it on the string "Ruby" together with "<3" so that you get the following string back:
"Ruby<3<3<3"








