# Ruby each_cons

## Iterates the given block for each array of consecutive <n> elements. If no block is given, returns an enumerator.

```
2.7.0 :004 > [1, 2, 3, 4, 5, 6].each_cons(2) { |pair| p pair }
[1, 2]
[2, 3]
[3, 4]
[4, 5]
[5, 6]
```

```
2.7.0 :012 > ['a', 'b', 'c', 'd', 'e', 'f'].each_cons(3) { |letter| p letter }
["a", "b", "c"]
["b", "c", "d"]
["c", "d", "e"]
["d", "e", "f"]
```

```
2.7.0 :013 > [2, 4, 6, 1, 3, 9 , 12].each_cons(2).map { |pair| pair.sum.even? }
 => [true, true, false, true, true, false]
 ```
 