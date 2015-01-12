We haven’t really covered the other basic types in Ruby: numbers, strings, ranges and regular expressions.

## Numbers
Ruby supports integers and floating-point, rational, and complex numbers (normally -1073741824 ... 1073741823 or -4611686018427387904 ... 4611686018427387903).

```
num = 10001 4.times do
puts "#{num.class}: #{num}" num *= num
end

produces:
       Fixnum: 10001
       Fixnum: 100020001
       Fixnum: 10004000600040001
       Bignum: 100080028005600700056002800080001
```

Unlike other programming languages where you have to manage conversion Ruby does it automatically.

Ruby includes support for rational and complex numbers but doesn’t have a literal syntax for representing rational and complex numbers. Instead, you create them.

```
Rational(1, 4) + Rational(1, 4) # => (1/2)

Complex(1, 2) + Complex(1, 4)   # => (2+6i) 
```

## Strings
Ruby strings are simply sequences of characters. Strings are often created using string literals—sequences of characters between delimiters. `''` , `""`. Technically, Ruby does not have a class for characters—characters are simply strings of length one. 

## Ranges 
Ranges occur everywhere: January to December, 0 to 9, a to z. 

`(1..10).to_a # => [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]`

`('a'..'c').to_a # => ['a','b','c']`

Yes ! Ruby knows the ABC