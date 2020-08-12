# Heroku Workflow
You have to be in Git master

Run in terminal:
```
$ heroku login
```
then run code below
```
$ heroku create {name}
```
Change name with name of your application. If you don't choose a name Heroku creates one.

Run
```
$ git push heroku master
```
It takes a while, depends on the size and gems of your application

Then run
```
$ heroku run rake db:migrate
```
This creates and migrates your database

And if you need the seed
```
$ heroku run rake db:seed
```
To drop the database:
```
$ heroku pg:reset DATABASE_URL
```
end then to recreate the database with nothing in it:
```
$ heroku run rake db:migrate
```
To fetch your logs, use command:
```
$ heroku logs
```
To see status of Heroku server>
```
$ heroku ps
```
And to restart Heroku server
```
$ heroku restart -a apname
```
and thats it !!