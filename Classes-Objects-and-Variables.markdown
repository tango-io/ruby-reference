## Classes

Everything we manipulate in Ruby is an object. And every object in Ruby was generated either directly or indirectly from a class. Let's build a Dog class in Java

```
class Dog {

}
```

Cool, What properties does a Dog have? Usually a dog has a name and breed

```
class Dog {

  private String name;
  private String breed;

}
```

Now that we have the properties let's create the Setters and Getters

```
class Dog {

  private String name;
  private String breed;

  public void setName(String name) {
    this.name = name
  }

  public void setBreed(String breed) {
    this.breed = breed
  }

  public String getName(){
    return this.name
  }

  public String getBreed(){
    return this.breed
  }

}
```

Also, we want to set the properties when our dog is created

```
class Dog {

  private String name;
  private String breed;

  public Dog(String name, String breed){
   this.name = name;
   this.breed = breed;
  }

  public void setName(String name) {
    this.name = name;
  }

  public void setBreed(String breed) {
    this.breed = breed;
  }

  public String getName(){
    return this.name;
  }

  public String getBreed(){
    return this.breed;
  }

}
```

To finish our Dog class let's add a bark method

```
class Dog {

  private String name;
  private String breed;

  public Dog(String name, String breed){
   this.name = name;
   this.breed = breed;
  }

  public void setName(String name) {
    this.name = name;
  }

  public void setBreed(String breed) {
    this.breed = breed;
  }

  public String getName(){
    return this.name;
  }

  public String getBreed(){
    return this.breed;
  }

  public String bark(){
    return "Woaf Woaf";
  }

}

```

We have our class, properties and methods we are ready to create a dog

```
class TestDog {

  public static void main(String args[]){

    Dog scooby = new Dog("scooby","gran danes");
    System.out.println(scooby.bark() + "Hello my name is" + scooby.name);

  }

}
```


I know that is a lot of code, let's use Ruby instead of Java

```
class Dog
  attr_accessor :name, breed

  def initialize(name, breed)
    @name, @breed = name, breed
  end

  def bark
    "Woaf woaf"
  end
end

scooby = Dog.new('scooby', 'gran danes')

puts "#{scooby.bark} Hello my name is #{scooby.name}"
```

Classes in Ruby are defined using `class`, the symbols that are next to `attr_accessor` are the properties, `attr_accessor` means that any property can be set and get; also exist `attr_reader` and `attr_writer` as we saw before, methods are defined with `def` and the constructor is defined creating an `initialize` method

![amazing](https://encrypted-tbn3.gstatic.com/images?q=tbn:ANd9GcRzNOxatz59AYT3smpt1p-pRHPG_e5_YcVHGts9fXux7ViLmlsAfWbDIU4)

## Methods(class and instance)

To use the method `bark` we needed to instance the object Dog in scooby, this are the `instance methods`.

In other programming languages you probably used `Math.round(1.3)`, you didn't need to instance the class Math to use the `round` method, this methods are the `class methods`

```
class Dog
  self.bark
    puts "woaf woaf"
  end
end

Dog.bark
```

## Access Control

When designing a class interface, it’s important to consider just how much of your class will be exposed to the outside world. Allow too much access into your class, and you risk increasing the coupling in your application <== "and you risk increasing the coupling in your application" I think that sentence can be improved.

Ruby gives you three levels of protection:

* **Public methods** can be called by anyone—no access control is enforced. Methods are
public by default (except for the initialize, which is always private).

* **Protected methods** Access is kept within the family.

* **Private methods** cannot be called with an explicit receiver—the receiver is always the current object, also known as self. This means that private methods can be called only in the context of the current object

You specify access levels to methods within class or module definitions using one or more of the three functions public, protected, and private.

```
class MyClass
  def method1
  end

  protected
  def method2
  end

  private
  def method3
  end
end
```
