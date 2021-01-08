# Rails has_one vs belongs_to

They do the same thing. The only difference is on what side of the relationship you are.

If a User has a Profile:

```
class User
  has_one :profile
  ....
end
```

```
class Profile
  belongs_to :user
  ....
end
```

To determine who has the other project, we look at the foreign key.
We would say that the User has a Profile because the profiles table has a user_id column.

