# Rails model validation for two columns together

We have a Model with different columns, and we need a validation for two columns together.
Model Item with name and manufacturer. There should not be items that share identical name and manufacturer

```
class Item < ActiveRecord::Base
  validates :name, uniqueness: { scope: :manufacturer }
end
```
