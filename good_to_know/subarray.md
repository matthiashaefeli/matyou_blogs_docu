## Get all subarrays in Ruby

```
def subarray(array)
  sub_arrays = []
  array.length.times do |x|
    arr = array[x..-1]
    arr.length.times do |y|
      sub_arrays << arr[0..y]
    end
  end
  sub_arrays
end
```

```
2.0.0-p648 :031 > subarray [1,2,3,4]
 => [[1], [1, 2], [1, 2, 3], [1, 2, 3, 4], [2], [2, 3], [2, 3, 4], [3], [3, 4], [4]]
```

