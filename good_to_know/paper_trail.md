# How to search for specific attribute on the object serialized field

rails:
```
PaperTrail::Version.where(item_type: 'something').where_object(id: some_id)
```

sql
```
SELECT *
FROM paper_trail_versions
WHERE item_type = 'something'
AND object LIKE '%id: some_id%'
```
