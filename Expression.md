We’ve been fairly cavalier in our use of expressions in Ruby, I don't need to explain you this:

`plus = number_one + number_two`

This is pretty basic, you will be able to write code with out reading this part but it wouldn’t be as much fun.

As we said before, by default Ruby returns the end statement, not only in methods, anything that can reasonably return a value does. For example: <== is it the "end" statement? I think it isn't but the last line of the body of a function (if it's a function for instance).

`[ 3, 1, 7, 0 ].sort.reverse # => [7, 3, 1, 0]`

The method sort returns the sorted array and we can apply more methods to this array. Very obviously, isn't it ? But what if I tell you something that you probably you don't know

```
rating = case votes_cast
￼when 0...10
  Rating::SkipThisOne
when 10...50
  Rating::CouldDoBetter
else
  Rating::Rave
end
```

![surprise](http://tooply.com/photo/item/570/5341006757412.jpg)

As we said before: `Anything that can reasonably return a value does`

## Operator Expressions

Most programming languages manage the `Assignment` concept and you know what it is.

```
a = 3
b = 5
c = a + b
```

You can do this much more cleanly in Ruby:

```
a, b = 1, 2      => #a=1, b=2
a, b = b, a      => #b=2, a=1
```

Ruby lets you have a comma-separated list of values (the things on the right of the assignment).

## Conditional Execution

Ruby has several different mechanisms for conditional execution of code; most of them should feel familiar.
However, before we get into them we need to spend a short time looking at boolean expressions.

Ruby has a simple definition of truth. Any value that is not nil or the constant false is true.

### And, Or, and Not

Ruby supports all the standard boolean operators.

`nil && 99`

`nil || 99`

`!false`

## if and unless Expressions

An if expression in Ruby is pretty similar to if statements in other languages:

```
artist = "Shakira"

if artist == "Taylor Swift"
  puts "Hatters gonna hate hate hate (8)"
elsif artist == "Shakira"
  puts "Por que esto es africa !! Jungle eh eh (8)"
else
  puts "The artist is not in the playlist"
end
```

Ruby also has a negated form of the if statement:

```
unless duration > 180
  listen_intently
end
```

The unless statement does support else, but most people seem to agree that it’s clearer to switch to an if statement in those cases.

### case Expressions

The Ruby case expression is a powerful beast: a multiway if on steroids. And just to make it even more powerful, it comes in two flavors. <== "if on steroids"??

The first form is fairly close to a series of if statements; it lets you list a series of conditions and execute a statement corresponding to the first one that’s true:

```
case
when song.name == "Shake it off"
  puts "I love you Taylor Swift"
when song.duration > 120
  puts "Too long!"
end
```

The second form of the case statement is probably more common. You specify a target at the top of the case statement, and each when clause lists one or more comparisons to be tested against that target:

```
case command
when "byobu"
  puts "opening session ..."
else
  print "Illegal command: #{command}"
end
```

### Loops

Ruby has pretty primitive built-in looping constructs.

```
for i in 1..10 do
 puts i
end
```

```
i = 1
while i <= 10
  puts i
  i++
end
```

Those loops are very common in Programming Languages, but we are forgetting something ...

![this is ruby !](http://cdn.meme.am/instances/56277206.jpg)

Ruby has a friendly syntax to declare loops

```
3.times do |x|
 puts x
end
```

```
1.upto(100) do |x|
  puts x
end
```
