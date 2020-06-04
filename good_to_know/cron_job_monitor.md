# How to use the cron job monitor

=> Dashboard in IT => Cron Job Monitor

=> Add new cron job to monitor

Cron Job Name: Shuld be a name without space or special character.

Example: test_cron_job_name

Schedule: copy paste the schedule of the cron job

Example: 10 * * * *

The monitor converts the cron job schedule to ruby time.

On the row of the cron job push button copy text to copy what we need to add to the cron job.

Open crontab with editer: crontab -e

Add the line at the end of the cron job command

Example: 0,12,22,32,42,52 * * * * /home/bti_admin/bin/updatelogs.sh && curl https://bti-usa.com/cron_job_monitor/monitor/updatelogs=8D1R0S-I956-ZPSSBB >/dev/null 2>&1

exit and save.

That's it