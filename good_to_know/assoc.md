# Ruby assoc

search through an array of arrays and returns first array whose first element is given param

```
2.7.0 :001 > array = [['a', 'b', 'c'], ['d', 'e', 'f'], ['g', 'h', 'i']]
2.7.0 :002 > array
 => [["a", "b", "c"], ["d", "e", "f"], ["g", "h", "i"]]
2.7.0 :003 > array.assoc('a')
 => ["a", "b", "c"]
2.7.0 :004 > array.assoc('i')
 => nil
2.7.0 :005 > array.assoc('d')
 => ["d", "e", "f"]
2.7.0 :006 > array.assoc('e')
 => nil
2.7.0 :007 > array = [['a', 'b', 'c'], ['d', 'e', 'f'], ['a', 'h', 'i']]
2.7.0 :008 > array.assoc('a')
 => ["a", "b", "c"]
```
