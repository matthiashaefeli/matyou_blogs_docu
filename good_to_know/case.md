# Ruby case with regex

```
2.7.2 :014 > string = 'hello world'
 => "hello world"
2.7.2 :015 > case string
2.7.2 :016 > when /abc/
2.7.2 :017 >   puts 'abc'
2.7.2 :018 > when /hell/
2.7.2 :019 >   puts 'hell'
2.7.2 :020 > end
hell
```
