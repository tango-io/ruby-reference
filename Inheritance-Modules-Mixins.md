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

