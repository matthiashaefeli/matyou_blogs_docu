# Javascript Array.from()

Array.from() lets you create Arrays from array-like objects or iterable objects

Array from a String
```
Array.from('hello world')
> (11) ["h", "e", "l", "l", "o", " ", "w", "o", "r", "l", "d"]
```

Array from a Set
```
const set = new Set([1,2,3,1,2,3])
set
> Set(3) {1, 2, 3}
Array.from(set)
> (3) [1, 2, 3]
```

Array from a Map
```
const map = new Map([['key1', 1], ['key2', 2], ['key3', 3]])
map
> Map(3) {"key1" => 1, "key2" => 2, "key3" => 3}
Array.from(map)
> (3) [Array(2), Array(2), Array(2)]
> 0: (2) ["key1", 1]
> 1: (2) ["key2", 2]
> 2: (2) ["key3", 3]
> length: 3
Array.from(map.keys())
> (3) ["key1", "key2", "key3"]
Array.from(map.values())
> (3) [1, 2, 3]
```

Array from arguments
```
function myFunction() {
  return Array.from(arguments)
}
myFunction('a', 1, { 'key': 'val' })
> (3) ["a", 1, {…}]
> 0: "a"
> 1: 1
> 2: {key: "val"}
>length: 3
```
