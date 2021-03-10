# Rails and mailcatcher

If we need to catch emails on the development env, there is no better way to do it with mailcatcher

first install mailcatcher
```
$ gem install mailcatcher
```

do not put mailcatcher gem into your gemfile, It will conflict with your applications gems at some point

if you get an error installing it try with this flag

```
$ gem install mailcatcher -- --with-cflags="-Wno-error=implicit-function-declaration"
```

start mailcatcher server:

```
$ mailcatcher
```

go to http//127.0.0.1:1080/

change in environments/development.rb

```
config.action_mailer.delivery_method = :smtp
config.action_mailer.smtp_settings = { :address => '127.0.0.1', :port => 1025 }
config.action_mailer.raise_delivery_errors = false
```

send email and check on the ui.
