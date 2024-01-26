
<h3> INSTALLING LDAP ON CENTOS-7 </h3>


1. 
```
yum install -y openldap openldap-clients openldap-servers migrationtools -y
```

The following Will install ldap service 

```
systemctl start slapd
```
2. 
The following will start the ldap service

```
systemctl enable slapd
```

The following will enable the ldap service


```
slappasswd
```
4. slappasswd
The following will configure the password for ldap
