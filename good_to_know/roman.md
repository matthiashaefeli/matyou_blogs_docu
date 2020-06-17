# Roman number to arabic with Ruby

First we create a hash with the roman as the key numbers and the arabic numbers as the value.

```
@data = {
  'M' => 1000,
  'CM' => 900,
  'D' => 500,
  'CD' => 400,
  'C' => 100,
  'XC' => 90,
  'L' => 50,
  'XL' => 40,
  'X' => 10,
  'IX' => 9,
  'V' => 5,
  'IV' => 4,
  'I' => 1
}
```

Then we create the function.

First we set the result to 0. Then we loop over each key in the hash and check if the first index of the given roman number is a key in the hash. If we find the key we add the value to the result. Then we delete the key in the roman number.

```
def converter(roman)
  result = 0
  @data.each do |key, val|
    while roman.index(key) == 0
      result += val
      roman.slice!(key)
    end
  end
  result
end
```

```
2.0.0-p648 :027 > converter('MMCMDCDCXCLXLCIXVIVI')
 => 4080
```

```
2.0.0-p648 :028 > converter('XIV')
 => 14
```

