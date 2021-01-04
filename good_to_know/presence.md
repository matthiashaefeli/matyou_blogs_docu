# Rails presence

```
[].presence
=> nil
```

Returns the receiver if it's present otherwise returns nil

it is the same as:
```
object.present? ? object : nil
```
