<h2> What is NFS? </h2>
<br>
Network File System (NFS) is a protocol that allows you to share directories and files with other Linux clients over a network.

Shared directories are typically created on a file server, running the NFS server. Users can add files and folders to them, which are then shared with other users who have access to the folder or file.

- Port#: 2049

- Relies on TCP 

- OSI-Layer-4 


<h2> How to install NFS?:</h2>

install nfs using the command below, either with yum or dnf, the package includes the necessary utilities and daemons for NFS (Network File System) server and client support.
<br>
The Autofs service is optional but highly recommended. Autofs provides functionality to automatically mount filesystems when they are accessed and unmount them when not in use."

<br>
```
yum install nfs-utils autofs
```

Start the NFS service
<br>
```
systemctl start nfs-server.service 
```

Enable the NFS service
<br>
```
systemctl enable nfs-server.service
```

<br>
Alternatively you can use enable NFS by running the command below, this will start and enable the service in one command, command 
```
systemctl enable --now nfs-server.service
```

<br>
Checking the status of the NFS service
```
systemctl status nfs-server.service
```


<h2> NFS SERVER SETUP <h2>

Make a directory where you would like to mount the shares "folder", The path can be of your choice.

```
mkdir -p /mnt/docs 
```
<br>


Next change the ownership of the directory to nobody, which gives the bare minimum permissions to the user, as it does not require it
```
chown -R nobody: /mnt/docs
Nobody: is known as a service account  
```
<br>

Next configure the permissions of the shares, 660 is typically used, but this all depends on ussage and perference
```
chmod -R 777 /etc/mnt/docs
```
<br>


(OPTIONAL) Next list the permissions of the directory, to verify the changes made.
```
ls -ld /etc/mnt/docs
```
<br>

<br>
Restart the nfs service for the changes to take effect 
````
systemctl restart nfs-server.service
```


In exports configuration file, specify the path and (client-ip)  E.X  BELOW

vi /etc/exports 

```
/etc/mnt/docs  192.168.50.78/24 (rw, sync,no_all_squash,no_root_squash)
```


<br>
ro / rw 
ro : allow clients read only access to the share.
rw : allow clients read and write access to the share.

<br>
sync / async 
sync : NFS server replies to request only after changes made by previous request are written to disk.
async : specifies that the server does not have to wait.

<br>
wdelay / no_wdelay :
wdelay : NFS server delays committing write requests when it suspects another write request is imminent.
no_wdelay : use this option to disable the delay. no_wdelay option can only be enabled if the default sync option is enabled.

<br>
no_all_squash / all_squash :
no_all_squash : does not change the mapping of remote users.
all_squash : to squash all remote users including root.

<br>
root_squash / no_root_squash :
root_squash : prevent root users connected remotely from having root access. Effectively squashing remote root privileges.
no_root_squash : disable root squashing.
