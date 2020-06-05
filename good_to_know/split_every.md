# Ruby string split every nth character

```
2.7.0 :001 > 'hello world'.scan(/.{2}/)
 => ["he", "ll", "o ", "wo", "rl"]
2.7.0 :002 > 'hello world'.scan(/.{4}/)
 => ["hell", "o wo"]
```
