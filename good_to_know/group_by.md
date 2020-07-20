# Ruby group_by

Groups the collection by result of the block. Returns a hash where the keys are the evaluated result from the block and the values are arrays of elements in the collection that correspond to the key.

```
2.7.0 :001 > a=(1..6).to_a
2.7.0 :002 > a
 => [1, 2, 3, 4, 5, 6]
2.7.0 :003 > a.group_by { |n| n%2 }
 => {1=>[1, 3, 5], 0=>[2, 4, 6]}
2.7.0 :004 > a=[1,2,2,3,3,4,4,4,4,5]
2.7.0 :005 > a.group_by { |n| n }
 => {1=>[1], 2=>[2, 2], 3=>[3, 3], 4=>[4, 4, 4, 4], 5=>[5]}
```

```
2.7.0 :006 > hash = {"Chair" => 30, "Table" => 40, "Bed" => 60, "stool" => 20}
2.7.0 :007 > value = 30
2.7.0 :008 > hash.group_by do |k, v|
2.7.0 :009 >   v > value ? 'Big' : 'Small'
2.7.0 :010 > end
 => {"Small"=>[["Chair", 30], ["stool", 20]], "Big"=>[["Table", 40], ["Bed", 60]]}
```
