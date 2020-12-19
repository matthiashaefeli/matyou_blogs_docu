# Double Pipe Equals

```
a ||= b
```
Is the same as
```
a || a = b
```

This operator is used to create methods like the one below in your class.
You can have other method calling this method and get the result but it will be created only the first time.

```
def second_comments
  @second_comments ||= Blog.comments.where(second: true)
end
```
  