# Declare unknown id

If you have to write a migration to the sql and use the new id for another table but you don't know the id, you have to find the entrance and store the id in a variable.

we have two tables:

```
user_table
id  name  age
1   Carl  10
2   Beto  12
..
..
```

```
school_table
id  user_id room
1   1       2
2   2       2
..
..
```

Now we add a user to the user_table but we don't know what id he gets. First we add the user to the table:

```
INSERT INTO user_table (name, age)
VALUES ('Kurt', 12)
```
Then we search for that user and store it's id in a variable

```
DECLARE @UserId int
SELECT @UserId = id FROM user_table WHERE name = 'Kurt' AND age = 12
```

Then we use the variable to add to the other table:
```
INSERT INTO school_table (user_id, room)
VALUES (@UserId, 1)
```
