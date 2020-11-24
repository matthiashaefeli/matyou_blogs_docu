# How to rollback a specific migration

If the migration you want to rollbakc is the last one applied:

```
rake db:rollback STEP=1
```

If you change the number to a 5 for example, it would rollback migrations: 4, 3, 2, 1

To rollback only one specific migration use:

```
rake db:migrate:down VERSION=23948723948723489
```

This will only rollback the specific version. If that is not what you intented, you can safely run ```rake db:migrate``` and it will re-run only that one, skipping any others that where not previously rolled back.
