<br>
Shows the ip address similar to ifconfig / ip -4 a

``` 
ip addr show 
```

<br>
Shows the links

```
ethtool [nic-name]
```

<br>
Dislays the routing of the network

```
ip r 
```
<br>
Displays the specific interface's(NIC) MAC address is connected to, and how long to keep the ARP entry within the table. Also the mac address of default gateway.

```
arp -a 
```

<br>
Print the routing table, The route command helps to establish traffic being distrubted through network connections.

```
route 
```

<br>
Netstat is a powertool which can be used to display various important network related information, such as open ports, connected ports, type of protcol, routing and more. 

- a all 
- n network  
- t tcp  
- p protocol 
- r routing 
- l listening

```
netstat -antperl 
```
<br>
nmap is a useful utility tool which can scan for open ports 
- p port  
- -p- scans all ports 0-65535 

```
nmap -p 1-100 10.0.0.77 
```

<br>
Removes the specified port
- k kill 
- n number port

```
fuser -k -n tcp 22 
```

<br>
The “-iflist” option is used to display routes and host interface information. 

```
nmap -iflist
```

<br>
<br>

<h2> Network Manager Command Line Interface (NMCLI) </h3> 
<h4> Used on enterprise linux distros such as Oracle/Redhat/Centos/Fedora  </h4>

<br>
The Graphic User Interface (GUI) version of nmcli 

```
nmtui
```

<br>
Display a cheat-sheet for nmcli configuration

```
curl cheat.sh/nmcli
```

<br>
Show the state, and various  of the interface described  connection information 

```
nmcli con show [ens160] <----- 
```

<br>
Show the permissions of the connected NIC 

```
nmcli general permissions
```

<br>
View the status of the state 

```
nmcli general status
```

<br>
Check the status of connected and disconnected NIC devices.

```
nmcli dev
```

<br>
To add a and apply an interface  to a network adapter.

```
nmcli con add con-name “en2” ifname “eth0” type "ethernet"  ipv4.adresses 10.0.0.1/24 ipv4.gateway 10.0.0.1
```

<br>
Delete the configured interface for the particular connection-name specified

```
nmcli con delete [Name]
```

<br>
Once the settings have been configured properly, you can bring the interface up to utilize it.

```
nmcli con up [Name] <----- NETWORK-ADAPTER-NAME
```

<br>
To Assign a secondary, ip address to the interface use the + or if you want to remove the secondary IP address use the - as shown below
- Remove
+ Add

```
nmcli con mod [Name] +ipv4.addresses 10.0.0.75/24
```

<br>
Configure the auto-connect capabilities for the given interface name

```
nmcli con mod [Name] connection.autoconnect yes
```

<br>
To change the connection name.

```
nmcli con mod “current-name” connection.id “new-name”
```

<br>
Puts the nic (network interface card) into active state for Debian based Dsitros such as Ubuntu, Kali, Mint.

```
ifup nicname 
```


If this error occurs, 👉🏽 “ linux unknown error /etc/sysconfig/network-scripts/ “
This means that there is a conflict with the UUID.

<br>
Puts the nic (network interface card) into deactived state. for Debian based Dsitros such as Ubuntu, Kali, Mint.

```
ifdown nicname 
```

<br>
Will generate a new uuid, which you can input into 

/etc/sysconfig/network-scripts/
```
uuidgen [NIC-Name]
```

