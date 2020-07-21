# Ruby reverse 

First we need to know how to swap elements in an array

```
2.7.0 :020 > def swap(array, index1, index2)
2.7.0 :020 > def swap(array, index1, index2)
2.7.0 :021 >   temp = array[index1]
2.7.0 :022 >   array[index1] = array [index2]
2.7.0 :023 >   array[index2] = temp
2.7.0 :024 > end
 => :swap
2.7.0 :025 > array = [1,2,3,4]
2.7.0 :026 > index1 = 0
2.7.0 :027 > index2 = 3
2.7.0 :028 > swap(array, index1, index2)
 => 1
2.7.0 :029 > array
 => [4, 2, 3, 1]
```

Now we have spap the first element with the last element, andvance to the next element until it reaches the center.

```
2.7.0 :042 > def reverse_string(string)
2.7.0 :043 >   array = string.split('')
2.7.0 :044 >   i = 0
2.7.0 :045 >   j = array.length - 1
2.7.0 :046 >   while i < j do
2.7.0 :047 >     swap(array, i, j)
2.7.0 :048 >     i += 1
2.7.0 :049 >     j -= 1
2.7.0 :050 >   end
2.7.0 :051 >   array.join
2.7.0 :052 > end
 => :reverse_string
2.7.0 :053 > reverse_string('hello')
 => "olleh"
```
