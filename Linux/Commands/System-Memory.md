
Check for memory / cpu usage with Systemd systems
```
systemd-cgtop
```


Check swap memory 
```
smem -k -u -p -t
```

Displays: the total CPU usage 
```
top -O +%CPU
```

Displays: the total usage 
```
htop
```

Similar to top but more enhanced, must be installed,
```
glances
```

System Activity Report: Captures check swap memory 
```
sar -r 
```


- h human  | - m memory 
```
free -hm
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

