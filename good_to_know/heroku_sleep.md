# How to keep your free heroku app alive

One down side of the free tier by heroku is that your app is put to sleep after 30 mintues inactivity. It just means that your app might take 5-10 seconds to wake up.

The heroku free tier requires applictions to sleep a min of seven hours a day.

There are different ways to keep your app alive. You can write a method to ping yourself every 20 minutes, or you can check online for a tool that does this job for you.

I decided to check online. And found <a href="https://cron-job.org/en/">https://cron-job.org/en/</a>

Sign up and verify your email.

Once logged in go to Cronjobs and Create cronjob.

- add Title
- add http address
- schedule select User-defined
- select all days of month
- select all days of week
- select all months
- select hours from 7 to 23
- select minutes 29

Create cronjob and that's it