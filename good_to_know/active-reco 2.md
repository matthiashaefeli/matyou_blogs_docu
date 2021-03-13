# ActiveRecord and find or where

If you use .find() or .where(id: ....)

If the primary key is an integer find by id and where id coerces its arguments using to_i

that means:

```
2.7.2 :001 > '9898798-user_name'.to_i
 => 9898798
2.7.2 :002 >
```

```
Person.find(1)
=> returns object for id 1
Person.find('1')
=> returns object for id 1
Person.find('1-this-user)
=> returns object for id 1
```

