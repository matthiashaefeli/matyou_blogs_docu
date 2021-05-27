# What does the ! mean ?

```
!ENV['OK_TO_SEED']
```


```ENV['OK_TO_SEED']``` can be either nil or a string.

so ```!ENV['OK_TO_SEED']``` is true if ENV['OK_TO_SEED'] is nil and false if it's a string.

an equivalent here would be:

```
ENV.key?('OK_TO_SEED')
```