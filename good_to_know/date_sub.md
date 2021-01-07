# The DATE_SUB() function subtracts a time/date interval from a date and then returns the date

```
SELECT DATE_SUB("2021-01-01", INTERVAL 7 DAY);

=> 2020-12-22
```

```
SELECT CURDATE();

=> 2021-01-07
```


```
SELECT DATE_SUB(CURDATE(), INTERVAL 10 DAY);

=> 2020-12-28
```
