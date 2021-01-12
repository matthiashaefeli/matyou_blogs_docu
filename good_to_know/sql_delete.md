# How to drop all tables in MySQL

If you have some foerign key constraints, first you have to temporarily disable all the foreign key constraints.

```
SET FOREIGN_KEY_CHECKS = 0;
```

Then you can delete the tables like:

```
DROP TABLE IF EXISTS table_name
```

Or you can select all table on the UI tool and delete them all together.

Don't forget to turn on the foreign key constraint after it's done:

```
SET FOREIGN_KEY_CHECKS = 1;
```
