# Ruby regex to split a string every nth Character

```
2.7.0 :013 > '1234abcd5678efgh'.scan(/.{4}/)
 => ["1234", "abcd", "5678", "efgh"]
2.7.0 :014 > '1234abcd5678efgh'.scan(/.{2}/)
 => ["12", "34", "ab", "cd", "56", "78", "ef", "gh"]
```

```
2.7.0 :015 > '1234abcd5678efgh'.scan(/../)
 => ["12", "34", "ab", "cd", "56", "78", "ef", "gh"]
2.7.0 :016 > '1234abcd5678efgh'.scan(/..../)
 => ["1234", "abcd", "5678", "efgh"]
```
