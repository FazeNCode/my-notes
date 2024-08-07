What is Network bonding?
Network bonding also known as network aggregation or NIC teaming.



1.) Add two NIC cards to your virtual machine, which will be used for bonding

2.) Second step to network bonding, is to add a network type, use the command below. Runner - These are units of code written in JSON and are used for the implementation of various NIC teaming concepts, examples of runner modes include Round robbin, load balancing, broadcast, and active backup.
nmcli con add type team con-name team0 ifname team0 config '{"runner":{"name": "activebackup"}}'


3.) Third step is to modify the created network 
nmcli con modify team0 ipv4.addresses 192.168.235.150/24 ipv4.gateway 192.168.235.2 connection.autoconnect yes ipv4.method manual


4.) Fourth step is to add the slave connections and link it to our master team0 connection which is set "type team", refer to step 1.
NOTE: the ifname (interface name) will the be ones that have been added in step 1. To find out your interface name, run "nmcli dev" 
nmcli con add type team-slave con-name team0-port1 ifname ens224 master team0
nmcli con add type team-slave con-name team0-port2 ifname ens256 master team0


5.) Fifth step is to run the command below to check the status of network bonding. NOTE: replace team0 with the con-name which you have configured.
teamdctl team0 state

teamd - This is the nic teaming daemon that uses the libteam library to communicate with team devices via Linux Kernel.

rpm -qi teamd