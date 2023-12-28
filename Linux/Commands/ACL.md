<h3> WHAT IN THE HECK IS ACL?? </h3>

<p> 
Access control list (ACL) contains rules that grant or deny access to certain digital environments. There are two types of ACLs: Filesystem ACLs━filter access to files and/or directories.
Filesystem ACLs tell operating systems which users can access the system, and what privileges the users are allowed. 
</p>

```
-rw-rw-r--.  faze faze       168 Dec 21 19:53 text-file.txt
when we use ACL (access control list) the dot will be replaced by a +
-rw-r-----+   root faze         168 Dec 22 05:52 text-file.txt
```
<p>
In the /etc/fstab "defaults" means, ACL is turned on by default. 
In the older systems, users would have to manually add it in the /etc/fstab file, just as you would add / mount  virtual-disk-device  or nfs-service 
</p>

getfacl ["file-name"]
Output:
user::rw-
user:faze:r--
group::---
mask::r--
other::---

setfacl -m u:faze:4 ["file-name"]
-m stands for "modified actions"
u: stands for user ["user-name"]
:4 after user we can assign the file permissions accordingly

setfacl -x ["user-name"] file.txt
To remove the acl permissions from the file

setfacl -b file.txt 
to completely get rid of acl permissions 

setfacl --no-mask -m u:username:6 file.txt
To set ACL permissions with no mask. What is a mask?
A mask determines the maximum effective permissions have or are set,
Think of mask as a tracker, that tracks the permissions on directory/files

lsof
The lsof (list open files) common returns the user process that are actively using a file system it is sometimes helpful in determining why a file system remains in use and cannot be unmounted



