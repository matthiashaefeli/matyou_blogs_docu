# Rails API and session

To use session on a rails only api, we need to change following line in application.rb

```
config.api_only = false
```
to:
```
config.api_only = true
```
