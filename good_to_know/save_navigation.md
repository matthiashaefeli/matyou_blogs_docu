# Ruby save Navigation Operator

Imagine you have a School that has a Student and you want to get the Student's name. If you don't want to risk a nil error, you would do it this way:

```
if school && school.student && school.student.name
  #do something here
end
```
If school, or student is nil it would not return an error.

You can write the same example using the safe navigation operator:

```
if school&.student&.name
  #do something here
end
```

also check ActiveRecord try and dig