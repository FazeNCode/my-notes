What is Network bonding?
Network bonding also known as network aggregation or NIC teaming.



Teamd - This is the nic teaming daemon that uses the libteam library to communicate with team devices via Linux Kernel.

teamdctl - 

1.) First step to network bonding, is to add a network type, use the command below.
nmcli con add type team con-name team0 ifname team0 config '{"runner":{"name": "activebackup"}}'

2.) Second step is to modify the created network 
nmcli con modify team0 ipv4.addresses 192.168.235.150/24 ipv4.gateway 192.168.235.2 connection.autoconnect yes ipv4.method manual


3.) Third step is to add the slave connections and link it to our master team0 connection which is set "type team", refer to step 1.
nmcli con add type team-slave con-name team0-port1 ifname ens224 master team0
nmcli con add type team-slave con-name team0-port2 ifname ens256 master team0


4.) Run the command below to check the status of network bonding. NOTE: replace team0 with the con-name which you have configured.
teamdctl team0 state