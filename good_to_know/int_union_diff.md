# Intersection, Union and Difference off Arrays in ruby

`-` Difference - Returns a new array that is a copy of the first array with any items that also appear in second array removed.

`&` Intersection - Creates a new array from two existing arrays containing only elements that are common to both arrays. Duplicates are removed.

`|` Union - Concatenates two arrays. Duplicates are removed.

Examples:

```
food1 = ['pizza', 'hotdog', 'wurst', 'frits', 'pie']
food2 = ['pizza', 'hamburger', 'wurst']
```

The difference between the 2 arrays
```
2.7.0 :003 > food1 - food2
 => ["hotdog", "frits", "pie"]
```

Get the elements that are common to both arrays.
```
2.7.0 :004 > food1 & food2
 => ["pizza", "wurst"]
```

Union of the two arrays.
```
2.7.0 :005 > food1 | food2
 => ["pizza", "hotdog", "wurst", "frits", "pie", "hamburger"]
```
