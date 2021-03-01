# Do you need to know what changed after you update a Model in Rails

changes() returns a hash of changed attributes indicationg their original and new value like [originial_value, changed_value]

```
person.changes
=> {}
person.name = 'John'
person.changes
=> { 'name' => [nil, 'John'] }
person.name = 'Bill'
person.changes
=> { 'name' => ['John', 'Bill'] }
```
