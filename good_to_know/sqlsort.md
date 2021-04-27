# How to sort text with numbers in SQL

```
mysql> SELECT
data
FROM
mytable
ORDER BY
IF(data REGEXP '^[A-Z]',
CONCAT(
LEFT(data, 1),
LPAD(SUBSTRING(data, 3), 20, '0')),
CONCAT(
'@',
LPAD(data, 20, '0')
)),
LENGTH( data ),
	data;
```
