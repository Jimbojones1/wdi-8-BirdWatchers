## Monday Array and Hash excercise Answers

1. Create a array from the number one to a hundred.
 Loop through the array and puts to the console all the even
 numbers, if the number is odd put them into an empty array
 in descending order.

```
array = Array(1..100)
odd_array = []
array.each { |e|
  if e.even?
    p e
  else
    odd_array.push(e)
  end
}
p odd_array
```

2. Create an array from 'a' to 'z'. From that array
create a new array with all the vowels.

```
letters = Array('a'..'z')
vowels = letters.select { |letter| letter =~ /[aeiou]/}
```

3.  Create a hash containing 5 properties
    using symbols as key names.

```
morrison = {
  name: 'jim',
  band: 'doors',
  poet: true,
  alive: false,
  code_name: 'Mr. Mojo Risin'
}

p morrison.class
p morrison[:code_name]
```
4. Loop through the previous hash and print to the
   console "the key name is keyName and the value name is
   valueName"

```
morrison.each { |key, value|
  p "The key name is #{key} and value is #{value}"
}
```

5. Create a hash containing 5 properties using strings
  as the key names.

```
bird = {
  'name' => "Andrew Bird",
  'instrument' => "violin",
  'awesome'=> true,
  'album'=> 'Are You Serious',
  'song'=> 'left handed kisses'
}

p bird.class
p bird['name']
```

6.  loop through five and print keys and values

```
bird.each { |key, value|
  p "The key name is #{key} and value is #{value}"
}
```

7.  Create a Boolean value, hash value, array value
    and symbol value, and check what class they come from.  
    boolean

```
true.class
#hash
bird = {name:'jim'}
bird.class
# symbol
:age.class

```
