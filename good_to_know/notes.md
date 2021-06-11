# Get all TODO, OPTIMIZE and FIXME on the rails console

```
# Code Comments
    # TODO: domain_name_in_email needs to be implemented
    # OPTIMIZE: name_in_email is very slow and needs to be reworked
    # FIXME: email_upcase raises an exception
```

```
# Terminal
bin/rails notes

app/models/user.rb:
  * [ 5] [TODO] domain_name_in_email needs to be implemented
  * [ 9] [OPTIMIZE] name_in_email is very slow and needs to be reworked
  * [15] [FIXME] email_upcase raises an exception
```
