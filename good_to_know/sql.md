# Query to search for anything with specific name in SQL DB

```
SELECT DISTINCT a.name, a.xtype
FROM sysobjects a
INNER JOIN syscomments b on a.id = b.id
WHERE b.[text] LIKE '%search%'
```
