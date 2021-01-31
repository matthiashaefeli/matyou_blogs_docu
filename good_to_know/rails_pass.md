# Password validation with regex

```
class User < ApplicationRecord
  validate :password_valid?

  def password_valid?
    return if password_digest.match(/\A(?=.{8,})(?=.*\d)(?=.*[a-z])(?=.*[A-Z])(?=.*[[:^alnum:]])/x)
    errors.add :password, ': must have 8 characters, 1 Uppercase, 1 Lowercase, 1 Number, 1 Special Character'
  end
end
```

(?=.{8,})            at least 8 char longs
(?=.*\d)             one number
(?=.*[a-z])          one lowercase
(?=.*[A-Z])          one uppercase
(?=.*[[:^alnum:]])   one special char
