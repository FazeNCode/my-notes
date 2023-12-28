
yum install cronie
installs crontab, which you can use to configure automated tasks.

systemctl status crond.service

crontab -l
List all the cron jobs activated

crontab -e 
Create a cron job to automate task for the current user logged in

crontab -u user -e
Create a cron job to automate task for the root user or a specified user

