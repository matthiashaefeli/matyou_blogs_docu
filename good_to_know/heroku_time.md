# Change Time zone on Heroku
By default Heroku will return calls for current time in UTC
You can manually set your apps time zone adding a TZ environment variable via command line. If you wanted to set your default timezone to US Central time you would run code below on the command line
```
$ heroku config:add TZ="America/Chicago"
```
You can add the TZ variable via the Heroku dashbord to:

In your app dashboard navigate to 'settings'

Under 'config variables' click the 'reveal config vars' button

and set your variabale

TZ = America/Chicago
To check if it works, go to 'More' in your app dashboard click 'Run Console'

And type rails c

in the console type code below
```
Time.now
```
and thats it !!