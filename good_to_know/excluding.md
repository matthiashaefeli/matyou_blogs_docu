# Rails excluding

```
2.7.2 :004 > ['hello', 'World', 'and', 'more'].excluding('hello', 'World')
 => ["and", "more"]
2.7.2 :005 > [[1, 2], [3, 4], [5,6]].excluding([3, 4])
 => [[1, 2], [3, 4], [5, 6]]
```
