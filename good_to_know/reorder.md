# Ruby .reorder

Replaces any existing order with specified order

```
User.order('email desc').reorder('id asc')
```
this generate SQL ORDER BY id ASC

```
User.order('email desc').reorder('id asc').order('name asc')
```
generates SQL ORDER BY id ASC, name ASC
