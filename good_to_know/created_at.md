# Change created at only to date (Rails API)

```
def as_json
  super.merge('created_at' => self.created_at.strftime("%d-%m-%Y"))
end
```
