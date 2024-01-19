
<h3> What is a Cronjob?</h3>
<p>Cronjobs are jobs that are ran as an automated. </p>
<p> For example, if a user wants to display a message of the day (MOTD), every 4 hours, that can be done in the crontab, </p>

installs crontab, which you can use to configure automated tasks.
```
yum install cronie
```

Check the status of the cronie service
```
systemctl status crond.service
```

List all the cron jobs activated
```
crontab -l
```

Create a cron job to automate task for the current user logged in
```
crontab -e 
```

Create a cron job to automate task for the root user or a specified user
```
crontab -u user -e
```



