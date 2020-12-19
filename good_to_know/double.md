# Stars in arguments

```
2.7.0 :005 > def my_method(a, *b, **c)
2.7.0 :006 >   return a, b, c
2.7.0 :007 > end
 => :my_method
```

a is a regular parameter, *b will take all the parameters passed after the first parameter and put them in an array. **c will take any parameter given in the format key: value at the end of the method call.

```
2.7.0 :008 > my_method(1)
 => [1, [], {}]
2.7.0 :009 > my_method(1,2,3,4,5,6)
 => [1, [2, 3, 4, 5, 6], {}]
2.7.0 :010 > my_method(1,2,3,4,5,6, a: 1, b: 2)
 => [1, [2, 3, 4, 5, 6], {:a=>1, :b=>2}]
```
