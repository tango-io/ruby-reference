We’ve been fairly cavalier in our use of expressions in Ruby, I don't need to explain you this:

`plus = number_one + number_two`

This is pretty basic, you will be able to write code with out reading this part but it wouldn’t be as much fun.

As we said before, by default Ruby returns the end statement, not only in methods, anything that can reasonably return a value does. For example:

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