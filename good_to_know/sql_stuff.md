# SQL Stuff and FOR XML PATH

Adding FOR XML PATH to the end of a query allows you to output the results of the query as XML elements, with the element name contained in the PATH argument.

table:
```
id  name
1   John
2   Rob
3   Ruben
```
And the query to get all names in one row
```
SELECT ',' + name
FROM table_name
FOR XML PATH ('')
```
would return
```
,John,Rob,Ruben
```

Now we remove the leading comma with STUFF:
```
SELECT name = STUFF((
  SELECT ',' + name
  FROM table_name
  FOR XML PATH ('')
), 1, 1, '')
```

would return
```
John,Rob,Ruben
```

The STUFF statement literally "stuffs” one string into another, replacing characters within the first string.
and the paramaters for STUFF:
- the string to be stuffed
- the location to start deleting characters
- the number of characters to delete
