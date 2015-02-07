## What is Ruby ?

Ruby is a dynamic, open source programming language with a focus on simplicity and productivity. It has an elegant syntax natural to read and easy to write.

## Ruby Is an Object-Oriented Language

Almost everything in ruby is an object (having methods and properties):

`"Lorem Ipsum".reverse` => `"muspI meroL"`

`1.even?` => `false`

`"Lorem Ipsum".upcase` => `"LOREM IPSUM"`

`1.next` => `2`

Ruby syntax is "cleaner" than the syntax from other languages such as PHP or Java:

PHP:

`strrev("Lorem Ipsum")` => `"muspI meroL"`

Java:

`new StringBuilder("Lorem Ipsum").reverse().toString()` => `"muspI meroL"`

Ruby is wonderful, isn't it? It seems as if we told ruby what we want to do and ruby does it.

![wonderful](http://www.quickmeme.com/img/14/14d92dcc90a773e11cf2a9664a001b29039b0f0b9fd2e7729e19015bb53d89f5.jpg)

## Some Basic Ruby

As said before, ruby syntax is clean and readable, you don't need semicolons at the end of each statement, say goodbye to nightmares for compilation errors produced by semicolons.

Let's start learning more about ruby, we'll write a method that personalizes a greeting.

```
def say_hello(name)
  result = "Hello, " + name
  return result
end

#Let's begin to greet
say_hello("Ivan")<=
say_hello("Federico")

produces:
Hello, Ivan
Hello, Federico
```

Methods are defined with the keyword `def`, followed by the `method name`, the `method’s parameters`  between parentheses and you delimit the method body with the keyword `end`. Ruby comments start with a # character and run to the end of the line.

Writing a method in Ruby is easier than Java or other languages where you have to define what are you going to return at the end of the functions

> Java

```
String say_hello(String name){
  String result = "Hello, " + name;
  return result;
}
```

The methods looks very similar, right? Let's take the advantages of Ruby, What if I tell you that you that you don't need the `return` word, Ruby returns the last statement by default and we can do an expression interpolation.

```
def say_hello(name)
  "Hello, #{name}"
end
```

Within the string, the sequence #{expression} is replaced by the value of expression.

## Arrays and Hashes

Ruby’s arrays and hashes are indexed collections, an Object that groups multiple elements into a single unit. Collections are used to store, retrieve, manipulate, and communicate aggregate data. Typically, they represent data items that form a natural group and they are accessible using a key.

### Arrays example
```
prime_numbers = [1,2,3,5]  # array with four elements
puts "The first element is #{prime_numbers[0]}"
prime_numbers[0] = nil
puts "Now first element is #{prime_numbers[0]}"

produces:
The first element is `1`
Now first element is `nil`
```

You may have noticed that we used the special value `nil` in this example. In many languages, the concept of `nil` (or `null`) means “no object.” but this is Ruby and remember that everything in Ruby is an object even `nil`

### Hashes
A Hash is a collection of key-value pairs. It is similar to an Array, except that indexing is done via arbitrary keys of any object type, not an integer index.

Creates a new hash populated with the given objects. Equivalent to the literal { key => value, ... }.

```
food = {
  'spaghetti' => 'Italia',
  'sushi' => 'Japan',
  'tacos' => 'Mexico'
}

puts food['sushi']
puts food['tacos']
puts food['enchiladas']

produces:
"Japan"
"Mexico"
nil
```

## Symbols
Sometimes when we are coding we create meaningful names, for example:

```
NORTH = 1
SOUTH = 2

warrior_walk(NORTH)
```

Let's make it better, Ruby offers a cleaner alternative. `Symbols` are objects that represent names and some strings inside the Ruby interpreter.T hey are generated using the :name and :"string" literals syntax

```
walk(:north)
```

```
food = {
  :spaghetti => 'Italia',
  :sushi => 'Japan',
  :tacos => 'Mexico'
}

puts food[:sushi]
puts food[:tacos]
puts food[:enchiladas]

produces:
"Japan"
"Mexico"
nil
```

## Blocks & Iterators

Ruby blocks are definitely one of the coolest features in Ruby, they are chunks of code between braces or between do-end statements that you can associate with method invocations, almost as if they were parameters.

This is a ruby block:

```
{ puts "Hello" }
```

This is also a ruby block:

```
do
  puts "Hello"
end
```

A method can then invoke an associated block one or more times using the Ruby `yield` statement.

```
def call_block
  puts "The method was called"
  yield
  yield
  puts "End of method"
end

call_block { puts "In the block" }

produces:
The method was called
In the block
In the block
End of method
```

Also you can provide arguments to the call to yield, and they will be passed to the block.

```
def who_says_what
  yield("Jonatan", "I'm a javascript developer")
  yield("Cesar", "I'm a Ruby developer")
end

who_says_what {|person, phrase| puts "#{person} says #{phrase}"}

produces:
Jonatan says I'm a javascript developer
Cesar says I'm a Ruby developer
```

Code blocks are used throughout the Ruby library to implement `iterators`, which are methods that return successive elements from some kind of collection, such as an array:

```
animals = %w( ant bee cat dog ) # creates an array
animals.each {|animal| puts animal }

produces:
ant
bee
cat
dog
```
