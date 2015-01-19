Before to start we need to have very clear this concepts:

**Namespace**

A container which allows developers to bundle all functionality under a unique, application-specific name.

**Class**

Defines the characteristics of the object. It is a template definition of variables and methods of an object.

**Object**

An Instance of a class.

**Property**

An object characteristic, such as color.

**Method**

An object capability, such as walk. It is a subroutine or function associated with a class.

**Constructor**

A method called at the moment of instantiation of an object. It usually has the same name as that of the class containing it.

**Inheritance**

A class can inherit characteristics from another class.

**Encapsulation**

A method of bundling the data and methods that use them together.

**Abstraction**

The conjunction of complex inheritance, methods, properties of an object must be able to simulate a reality model.

**Polymorphism**

Poly means "many"  and morphism means "forms". Different classes might define the same method or property.


Everything we manipulate in Ruby is an object. And every object in Ruby was generated either directly or indirectly from a class. Let's build a Dog class in Java then in Ruby

```
class Dog {

}
```

Cool, What properties has a Dog? Usually a dog has a name and breed

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