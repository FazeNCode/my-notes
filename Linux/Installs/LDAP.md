
<h3> INSTALLING LDAP ON CENTOS-7 </h3>


1. yum install -y openldap openldap-clients openldap-servers migrationtools -y
The following Will install ldap service 

2. systemctl start slapd
The following will start the ldap service

3. systemctl enable slapd
The following will enable the ldap service

4. slappasswd
The following will configure the password for ldap
