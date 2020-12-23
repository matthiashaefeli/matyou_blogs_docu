# Define serializer type name

In the serializer you can define the type name of the serializer.

If you do not define the type name it would set the name of the serializer:
```
class UserSerializer
  ...
end
```

The type of the serializer above would be 'user'

```
class UserSerializer
  set_type: my_user
  ...
end
```

The type of the serializer above would be 'myUser'
