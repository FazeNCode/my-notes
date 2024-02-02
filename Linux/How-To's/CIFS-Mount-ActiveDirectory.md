<h3> CIFS Mount Ubuntu server with Windows Server  </h3>



<h3> Step 1: Install the necessary packages </h3>

Packages such samba, samba-client libnss-winbind winbind are used for more extensive intergration with Samba and Active Directory, such user authentication, user mapping.
```
apt install cifs-utils samba samba-client libnss-winbind winbind
```



<h3> Step 2: Create a folder to mount </h3>

```
mkdir /media/mount
```

Step 3: Create a folder on the windows machine 

Right click folder >> Properties >> Advance Sharing
Check mark: Share this folder
Click on >> Permissions >> Check mark: Full Control
Once Configured, the Network Path will be updated, which is used for mounting on the Linux machine.


Step 4: Edit the /etc/nsswitch.conf file, to put "wins" before dns
```
nano /etc/nsswitch.conf
```

hosts: files mdns_minimal [NOTFOUND=return] wins dns


Step 5: Make a credentials file on the specified user account, example listed below:

```
vi /home/david/.smbcred
```

username=Your_username@win.local
password=Your_password
domain=wins.local

Step 6: Edit the fstab file
First:  Windows machine name and the directory which we are going to mount to.
Second: Mount path on the linux machine
Third:  File sharing method
Fourth: Credential file path
Fifth:  Group ID / User ID 
Sixth:  Permissions on the on file and directory

//WINDOWSERVER/Mounted /media/mount cifs credentials=/home/ads@win.local/.smbcred,gid=966660001,uid=9666600001,file_mode=0777,dir_mode=0777 0 0

```
vi /etc/fstab
```


//cubisdata/cds /mnt/test-mount cifs	 rw,vers3.0,credentials=/etc/smbount.ea_linux_admin2,uid=15099,gid=15099,file_mode=0775,dir_mode=0775 0 0
```
vi /etc/fstab
```
