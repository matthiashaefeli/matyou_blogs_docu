# Ruby each_with_object

The most popular usage of each_with_object is putting hash or array as argument

If we have something like that:

```
array = ['hello', 'world', '1', 'hello']
```
and we want to create a hash with the string as the key and the count of each string as the value, you would do something like:

```
2.7.0 :045 > hash = {}
2.7.0 :046 > array.each do |e|
2.7.0 :047 >   hash.key?(e) ? hash[e] += 1 : hash[e] = 1
2.7.0 :048 > end
 => ["hello", "world", "1", "hello"]
2.7.0 :049 > hash
 => {"hello"=>2, "world"=>1, "1"=>1}
2.7.0 :050 >
```

With each_with_object we can do this giving the hash as a argument

```
2.7.0 :050 > array.each_with_object(Hash.new(0)) do |e, hash|
2.7.0 :051 >   hash[e] += 1
2.7.0 :052 > end
 => {"hello"=>2, "world"=>1, "1"=>1}
```

