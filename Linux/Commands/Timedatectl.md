Check the time configuration status on the machine
```
timedatectl
```


List all the available time-zones which can be configuered

```
timedatectl list-timezones
```



Set the time-zone to the preferred zone
```
timedatectl set-timezone “Asia/Kolkata”
```


Set the time-zone to the preferred time zone,

```
timedatectl set-timezone UTC
```


Set the machine time-zone to a specfic time of your choice.
```
timedatectl set-timezone 15:50:30 | Hour/Minute/Secnd
```



Set Network time protocol (true) to true to utilize the global synchronization of time-zone on your linux machine 
```
timedatectl set-ntp true
```
