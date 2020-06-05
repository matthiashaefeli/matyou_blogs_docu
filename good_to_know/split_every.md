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
