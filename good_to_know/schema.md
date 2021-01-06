# Rails and schema.rb

the version of the schema.rb should always be the version of the last migration name:

```
ActiveRecord::Schema.define(version: 2020_11_17_205641) do
  ...
end
```

last migration name:

```
20201117205641_create_users_table.rb
```
