# Ruby explain()

You can run EXPLAIN on the queries triggered by relations. For example,

```
User.where(id: 1).joins(:articles).explain
```

Active Record performs a pretty printing that emulates that of the corresponding database shell.