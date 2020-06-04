# Move a specific element of an array to the front

```
2.7.0 :046 > object = {a: 'third'}
2.7.0 :047 > array = [{a: 'first'}, {a: 'second'}, {a: 'third'}, {a: 'fourth'}]
2.7.0 :048 > array.select { |e| e != object }.unshift(object)
 => [{:a=>"third"}, {:a=>"first"}, {:a=>"second"}, {:a=>"fourth"}]
2.7.0 :049 > array
 => [{:a=>"first"}, {:a=>"second"}, {:a=>"third"}, {:a=>"fourth"}]
 ```

```
2.7.0 :050 > array = [{a: 'first'}, {a: 'second'}, {a: 'third'}, {a: 'fourth'}]
2.7.0 :051 > array.unshift(array.delete_at(2))
 => [{:a=>"third"}, {:a=>"first"}, {:a=>"second"}, {:a=>"fourth"}]
2.7.0 :052 > array
 => [{:a=>"third"}, {:a=>"first"}, {:a=>"second"}, {:a=>"fourth"}]
 ```
 