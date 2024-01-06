YellowDog Updater

<h6> YUM-Essentials: </h6>

Update the current repository 
```
yum update
```
Update the yum package manager
```
yum upgrade
```
Display services that have version lock.
```
yum versionlock list 
```

Delete the version lock on the specified service.
```
yum versionlock delete service-name 
```

Display installed aswell as not installed packages
```
yum list installed
```

Display history of installs.
```
yum history
```

Lists transactions (commands) recorded in yum history database.	
```
yum history list id_number	
```

Retrieve detailed information about a specific transaction recorded.
```
yum history info ID_Number 
```

Display all the repos on the machine.
```
yum repolist  
```

Display all the dependencies associated with nodejs package
```
yum deplist nodejs 
```
Display all the dependencies associated with nodejs package
```
yum search nodejs 
```

Display all the information related to nodejs package
```
yum info nodejs 
```

Display a query of information of nodejs package
```
yum repoquery -l nodejs
```


