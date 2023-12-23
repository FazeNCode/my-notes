
Display all the firewall configuration
```
firewall-cmd --list-all   
```
Display all the firewall configuration in the public zone
```
firewall-cmd --zone=public --list-all
```

Add a port to the firewalld 
```
firewall-cmd --permanent --add-port=82/tcp
```

Add and allow multiple services in one command
```
firewall-cmd --permanent --add-service={nfs,httpd,mountd}
```

Display configured system information for interface
```
firewall-cmd --get-zone-of-interface=ens256
```
