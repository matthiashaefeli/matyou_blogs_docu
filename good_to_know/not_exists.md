# How to select all records from one table that not exists in another table

```
SELECT a
FROM table1
WHERE a NOT IN (SELECT a FROM table2)
```

```
SELECT a
FROM table1
WHERE NOT EXISTS (SELECT *
                  FROM table2
                  WHERE table1.a = table2.a)
```

```
SELECT a
FROM table1
LEFT JOIN table2 ON table1.a = table2.a
WHERE table1.a IS NULL
```
