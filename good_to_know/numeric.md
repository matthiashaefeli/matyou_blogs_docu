# Ruby is string number?

This is a nice solution to check if a string is a Number

```
class String
  def numeric?
    Float(self) != nil rescue false
  end
end
```

```
2.7.0 :008 > '123'.numeric?
 => true
2.7.0 :009 > '123'.numeric?
 => true
2.7.0 :010 > '123a'.numeric?
 => false
2.7.0 :011 > 'aaa'.numeric?
 => false
```
