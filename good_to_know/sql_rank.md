# SQL Rank function

```
RANK() OVER(
  ORDER BY val
) AS rank
```

```
IF(val = @_last, @curRank := @curRank, @curRank := @_sequence) AS rank,
@_sequence := @_sequence+1,
@_last := val
...
...
...
...
(SELECT @curRank := 1, @_sequence := 1, @_last := 0) AS r
```
