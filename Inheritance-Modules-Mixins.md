## Inheritance

Inheritance allows you to create a class that is a refinement or specialization of another class. This class is called a subclass of the original, and the original is a superclass of the subclass. People also talk of child and parent classes.

```
class HowardStark
  def say_hello
    puts "I'm amazing"
  end
end

class TonyStark < HowardStark
end

ironman = TonyStark.new
ironman.say_hello
```

We then create a subclass using class `TonyStark < HowardStark`. The `<` notation means we’re creating a subclass of the thing on the right; the fact that we use less-than presumably signals that the child class is supposed to be a specialization of the parent.

Note that the child class defines no methods, but when we create an instance of it, we can call say_hello. That’s because the child inherits all the methods of its parent. 

## Modules

Modules are a way of grouping together methods, classes, and constants. Modules give you two major benefits:

  * Modules provide a namespace and prevent name clashes.
  * Modules support the mixin facility.


```
module Trig
  PI = 3.141592654
 
  def sin(x)
  end

  def cos(x)
  end 
end
```

Now We are able to include this module in our class

```
class Math
  extend Trig
end

Math.cos(12)
```

## Mixins

Modules have another, wonderful use. At a stroke, they pretty much eliminate the need for inheritance, providing a facility called a mixin.

You can include a module within a class definition. When this happens, all the module’s instance methods are suddenly available as methods in the class as well. They get mixed in. In fact, mixed-in modules effectively behave as superclasses.

```
module Flyer
  def fly
    puts "I believe I can fly"
  end
end

class Bird
  include Flyer
end

class Plane
  include Flyer
end

piolin = Bird.new
jayjay = Plane.new

piolin.fly
jayjay.fly
```