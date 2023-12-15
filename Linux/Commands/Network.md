Shows the ip address similar to ifconfig / ip -4 a
``` 
ip addr show 
```

Shows the links
```
ethtool [nic-name]
```


Dislays the routing of the network
```
ip r 
```

Displays the specific interface(NIC) a MAC address is connected to, and how long to keep the ARP entry within the table.
```
arp -a 
```


Print the routing table, this tells users where traffic exits.
```
route 
```

netstat is a powertool which can be used to display various important network related information, such as open ports, connected ports, type of protcol, routing and more. 

-a all  | - n network | -t tcp  | - p protocol | -r routing | -l listening
```
netstat -antperl 
```

nmap is a useful utility tool which can scan for open ports 
- p port  | -p- scans all ports 0-65535 
```
nmap -p 1-100 10.0.0.77 
```

Will remove the specified, port
- k kill  | - n number port
```
fuser -k -n tcp 22 
```

```
nmap -iflist
```

The “-iflist” option is used to display routes and host interface information. 







<h2> Network Manager Command Line Interface (NMCLI) </h3> 

Oracle/Redhat/Centos/Fedora 
The GUI version of nmcli 
```
nmtui
```

curl cheat.sh/nmcli
Display a cheat-sheet for nmcli configuration
nmcli con show [ens160] <----- 
Show the connection information 
nmcli general permissions
Show the connection permissions
nmcli general status
View the status of the state 
nmcli dev
Check the status of the device
nmcli con add con-name “en2” ifname “eth0” type "ethernet"  ipv4.adresses 10.0.0.1/24 ipv4.gateway 10.0.0.1


nmcli con delete [Name]
Delete the configured settings for the particular connection-name specified



nmcli con up [Name] <----- NETWORK-ADAPTER-NAME
Once the settings have been configured properly, you can bring the network-up to utilize it,
nmcli con mod [Name] +ipv4.addresses 10.0.0.75/24
The option to associate another ip address 
- Remove
+ Add
nmcli con mod [Name] connection.autoconnect yes
Configure the auto-connect capabilities for the given con-name
nmcli con mod “current-name” connection.id “new-name”

ifup nicname 
Will bring the nic (network interface card) up and running
If the error below occurs, 
“ linux unknown error /etc/sysconfig/network-scripts/ “
This means that there is a conflict with the UUID.
ifdown nicname 
Will bring the nic (network interface card) down

uuidgen [NIC-Name]
Will generate a new uuid, which you can input into 
/etc/sysconfig/network-scripts/
