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

<h4> Used on enterprise linux distros such as Oracle/Redhat/Centos/Fedora  </h4>

<br>
The GUI version of nmcli 
```
nmtui
```

Display a cheat-sheet for nmcli configuration
```
curl cheat.sh/nmcli
```

Show the state, and various  of the interface described  connection information 
```
nmcli con show [ens160] <----- 
```

Show the permissions of the connected NIC 
```
nmcli general permissions
```

View the status of the state 
```
nmcli general status
```

Check the status of connected and disconnected NIC devices.
```
nmcli dev
```

To add a and apply an interface  to a network adapter.
```
nmcli con add con-name “en2” ifname “eth0” type "ethernet"  ipv4.adresses 10.0.0.1/24 ipv4.gateway 10.0.0.1
```

Delete the configured interface for the particular connection-name specified
```
nmcli con delete [Name]
```


Once the settings have been configured properly, you can bring the interface up to utilize it,
```
nmcli con up [Name] <----- NETWORK-ADAPTER-NAME
```

Assign a secondary, ip address to the interface
- Remove
+ Add

```
nmcli con mod [Name] +ipv4.addresses 10.0.0.75/24
```

Configure the auto-connect capabilities for the given interface name
```
nmcli con mod [Name] connection.autoconnect yes
```


```
nmcli con mod “current-name” connection.id “new-name”
```

Puts the nic (network interface card) into active state for Debian based Dsitros such as Ubuntu, Kali, Mint.

```
ifup nicname 
```


If the error below occurs,
“ linux unknown error /etc/sysconfig/network-scripts/ “
This means that there is a conflict with the UUID.

Puts the nic (network interface card) into deactived state. for Debian based Dsitros such as Ubuntu, Kali, Mint.

```
ifdown nicname 
```


Will generate a new uuid, which you can input into 

/etc/sysconfig/network-scripts/
```
uuidgen [NIC-Name]
```

