# Ruby hash.invert

Hash#invert() is a Hash class method which gives the hash by reverting keys to values and values to key.

```
2.7.2 :001 > hash = { a: 1, b: 2, c: 3 }
 => {:a=>1, :b=>2, :c=>3}
2.7.2 :002 > hash.invert
 => {1=>:a, 2=>:b, 3=>:c}
```
