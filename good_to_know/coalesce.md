# SQL COALESCE

The COALESCE() function returns the first non null value in a list

```
SELECT COALESCE(NULL, NULL, 1, 'this text')
```
would return 1


You can use is also instead of a case statement.

```
SELECT
(CASE
  WHEN city IS NULL THEN country
  ESLE city
  END) AS place
FROM adrresses
```

```
SELECT
COALESCE(city, country) AS place
FROM adrresses
```
