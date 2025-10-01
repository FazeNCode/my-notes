<h3> How to create a partition on Linux </h3>


Use the fdisk command to enter the setup for creating a partition. 
Note: If you don't know your disk name, use the ```lsblk``` to list out your disks

```
fdisk /dev/your-disk-name
```


<h3> Now lets proceed to creating our physical volume </h3>

To create a Physical Volume
```
pvcreate /dev/partition-name
```

You can display the created physical volume by running  ```pvdisplay```
```
pvdisplay
```






Volume-Group

vgdisplay command display the current Volume groups
```
vgdisplay
```


To create a Volume group
```
vgcreate vgname /dev/partition-name
```




Logical-Volume

To display current Logical Volume
```
lvdisplay
```

To Create the Logical volume 

```
lvcreate -L 2G -n lvname/vgname  
```

To resize the logical volume
```
lvresize --size 1G /dev/volume/logical
```

To extend the logical volume 
```
lvextend -r -L +2G /dev/volume/logical
```

To remove the logical volume
```
lvremove /dev/volume/logical
```


mount -a 


In the image below you can see the nfs-client lvm is not present, This is because we have not created a file system yet.

