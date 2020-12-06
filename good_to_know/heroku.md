# Cloned Git repo from github. How to connect to heroku master

First login to heroku

```
$ heroku login
```

connect master to heroku master


```
$ git remote add heroku https://git.heroku.com/my_app_name.git
```

and push changes

```
$ git push heroku master
```

