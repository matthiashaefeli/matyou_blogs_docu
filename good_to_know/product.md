# Ruby .product

Product will create an array in an array from an array

```
2.7.2 :004 > a=[1,2,3,4,5]
 => [1, 2, 3, 4, 5]
2.7.2 :005 > a.product()
 => [[1], [2], [3], [4], [5]]
```

If given a block, product will yield all combinations

```
2.7.2 :006 > a=[1,2,3,4,5]
 => [1, 2, 3, 4, 5]
2.7.2 :007 > a.product([9, 10])
 => [[1, 9], [1, 10], [2, 9], [2, 10], [3, 9], [3, 10], [4, 9], [4, 10], [5, 9], [5, 10]]
```
