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