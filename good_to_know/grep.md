# Ruby .grep

You can use .grep to filer enumerable objects


use .grep to get only the strings
```
3.1.0 :001 > ['a', 'b', 1, 2, [1, 2], { a: 1 }, 'd'].grep(String)
 => ["a", "b", "d"]
```

use .grep to find all words starting with 'a'
```
3.1.0 :002 > ['aloha', 'beta', 'adam', 1, 2, { a: 1 }, 'd'].grep(/^a/)
 => ["aloha", "adam"]
```

use .grep to get a list of all the numbers in a range
```
3.1.0 :004 > [1, 2, 3, 4, 5, 6, 7].grep(3..5)
 => [3, 4, 5]
```

