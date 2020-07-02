# Ruby string split every nth character

```
2.7.0 :001 > 'hello world'.scan(/.{2}/)
 => ["he", "ll", "o ", "wo", "rl"]
2.7.0 :002 > 'hello world'.scan(/.{4}/)
 => ["hell", "o wo"]
```

If the number of characters isn't divisible by the number, you can also grab the remaining characters:

```
2.7.0 :003 > 'hello world'.scan(/.{1,4}/)
 => ["hell", "o wo", "rld"]
```

Or we can use slice and map

```
2.0.0-p648 :038 > '123456'.chars.each_slice(2).map { |s| s.join }
 => ["12", "34", "56"]
2.0.0-p648 :039 >
```
