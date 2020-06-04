# Convert string to operator in Ruby

There are two different ways to convert a ruby string into a math operator:

```
2.7.0 :001 > 4.public_send('+', 6)
 => 10
2.7.0 :002 > 4.public_send('-', 6)
 => -2
2.7.0 :003 > 4.public_send('*', 6)
 => 24
2.7.0 :004 > 10.public_send('/', 5)
 => 2
```

```
2.7.0 :001 > 4.method('+').(6)
 => 10
2.7.0 :002 > 4.method('-').(6)
 => -2
2.7.0 :003 > 4.method('*').(6)
 => 24
2.7.0 :004 > 10.method('/').(5)
 => 2
```
