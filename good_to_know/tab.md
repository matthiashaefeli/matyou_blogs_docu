# Ruby tap

Tap is a nice little method that improves code readability. See example below

```
class User
  attr_accessor :first_name, :last_name, :age
end
```

create a instance of the user class and asign the attributes:

```
def create_user_method
  user = User.new
  user.first_name = 'first'
  user.last_name = 'last'
  user.age = 40
  user
end
```
Or you could use tap to do it like this:
```
def create_user_method
  User.new.tap do |u|
    u.first_name = 'first'
    u.last_name = 'last'
    u.age = 40
  end
end
```
The tap method yields the calling object to the block and returns it.
