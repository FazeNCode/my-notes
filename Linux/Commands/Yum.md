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


<h6> YUM-Installs: </h6>

Mail Transfer Agent (MTA)  /etc/postfix/main.cf
```
yum install postfix
```

secure shell service
```
yum install sshd 
```
Used to configure automated tasks, also known as cron jobs
```
yum install cronie
```
Apache web server service
```
yum install httpd 
```
Used to monitor logs for the system
```
yum install rsyslog  
````
figlet allows user to customize their console output
```
yum install figlet
```
Installs Network file system along with Access Control List (ACL) for nfs, for fine tuning access permissions.
AutoMounter which gives the ability to automatically mount and unmount on demand,
```
yum install nfs-utils nfs4-acl-tools autofs
```
Installs Common Internet file system.
```
yum install cifs-utils
```
Installs dnf package manager, which is an updated version of yum also known as YUMv4, along with dnf utilities.
```
yum install dnf-utils
```

Installs utility to query DNS
```
yum install bind bind-utils -y
```


Installs various utilities tools for inspecting, and setting devices connected to the PCI bus
```
yum install pci-utils
```


Installs MySQL DataBase 
```
yum install mysql-server
```
Installs GNU Compiler Collection, which contains compilers for various languages such as, c/c++, Java, Rust, Go and more.. Installs libraries such as libstdc++ (Library Standard C++) also known as glibcxx (GNU library c),
GDB (GNU Debugger), libgcj (Library gnu compiler Java run time) along with many other libraries.
```
yum install gcc 
```
Installs Compiler and libraries specifically for C++ 
```
yum install gcc-c++ 
```
