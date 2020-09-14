# Do you need to know when a specific line was changed

```
$ git log -u -L 12,15:app/controllers/user_controller.rb
```

12 is the start of the line number to search for the changes

15 is the end of the line number to search for the changes