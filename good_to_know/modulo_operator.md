# Ruby Modulo Operator

The modulo operator gives you the remaining of a division. This can be used for things like checking if a number is even or odd.

```
2.7.0 :001 > 2%2
 => 0
2.7.0 :002 > 4%2
 => 0
2.7.0 :003 > 5%2
 => 1
```

So, if the result is 0 the number is even (no reminder means that the number is evenly divisible by 2)
If the result is any other number the number is odd.

We can use the Modulo Operator to check if a number is divisible by another number
```
2.7.0 :010 > 9%3
 => 0
2.7.0 :011 > 10%3
 => 1
2.7.0 :012 > 15%2
 => 1
2.7.0 :013 > 25%5
 => 0
```

If the result is 0 then the number is divisible by the other

Seconds to minutes

```
2.7.0 :027 > total_seconds = 5555
2.7.0 :028 > seconds = total_seconds % 60
2.7.0 :029 > seconds
 => 35
2.7.0 :030 > minutes = (total_seconds / 60) % 60
2.7.0 :031 > minutes
 => 32
2.7.0 :032 > hours = total_seconds / (60 * 60)
2.7.0 :033 > hours
 => 1
```
