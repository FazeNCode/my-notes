
Check for memory / cpu usage with Systemd systems
```
systemd-cgtop
```


- h human  | - m memory 
```
free -hm
```

Displays: the total CPU usage, alternatively you can use the top command to specficly show cpu usage, replace the MEM, to CPU to view cpu usage
```
top -O +%MEM 
```

Displays: the total usage in graphical interface look,
```
htop
```

Similar to top but more enhanced, must be installed.
```
glances
```

<p> Check swap memory </p>
```
smem -k -u -p -t
```





System Activity Report: Captures check swap memory 
```
sar -r 
```


Contains detailed information about the system's memory usage.
```
cat /proc/meminfo
```

Displays a snapshot of current processes, including memory usage.
```
ps aux --sort=-%mem
```

Will display the swappiness 
```
sysctl vm.swappiness
```



grep -iE 'killed process|oom' /var/log/messages | grep -iE 'Dec 21'

find out which process, UID was killed by OOM-Killer aswell as total-vm value which is the amount of memory the process requests before killing the process



id -nu 18798