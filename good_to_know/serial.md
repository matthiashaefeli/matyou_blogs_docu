# Rails Json Serializer

I needed to exclude a has_many relationship in a rails json serializer.

We used the fast_jsonapi gem. And thats what I found:

```
class MovieSerializer
  include FastJsonapi::ObjectSerializer

  # Actors will only be serialized if the record has any associated actors
  has_many :actors, if: Proc.new { |record| record.actors.any? }

  # Owner will only be serialized if the :admin key of params is true
  belongs_to :owner, if: Proc.new { |record, params| params && params[:admin] == true }
end
```

