Unit testing is testing that focuses on small chunks (units) of code, typically individual methods or lines within methods. This is in contrast to most other forms of testing, which consider the system as a whole.

Why focus in so tightly? It’s because ultimately all software is constructed in layers; code in one layer relies on the correct operation of the code in the layers below. If this underlying code turns out to contain bugs, then all higher layers are potentially affected. This is a big problem. 


## The Testing Framework

The Ruby testing framework is basically three facilities wrapped into a neat package:

 • It gives you a way of expressing individual tests.
 • It provides a framework for structuring the tests.
 • It gives you flexible ways of invoking the tests.

### Assertions == Expected Results

Rather than have you write series of individual if statements in your tests, the testing framework provides a set of assertions that achieve the same thing.

```
class Assassin
  def creed
    "Nothing is true, everything is permitted."
  end
end

class TestAssasin < Test::Unit::TestCase
  def test_creed
    assert_equal("Nothing is true, everything is permitted.", Assassin.new.creed)
  end
end
```

The assertion says that we’re expecting the Assassin creed should equal to `"Nothing is true, everything is permitted."`


Let's do It more complex tests

```
class Assassin
  attr_accessor :weapons

  def initialize
    @weapons = {:knife => 1, :sword => 2} 
  end

  def attack(enemy, weapon)
    enemy.life -= @weapons[weapon]
  end
end

class Templar
  attr_accessor :life

  def initialize
    @life  = 20
  end
end

class TestAssassin < Test::Unit::TestCase

  def test_assasin_weapons
    assert_equal({:knife => 1, :sword => 2}, Assassin.new.weapons)
  end

  def test_assasin_attack
    assert_equal(19, Assassin.new.attack(Templar.new, :knife))
  end
end

class TestTemplar < Test::Unit::TestCase
  def test_templar_life
    assert_equal(20, Templar.new.life)
  end
end

```