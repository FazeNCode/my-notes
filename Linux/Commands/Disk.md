
checks the disks on the device
```
fdisk -l
```

Check blocks on your device, disks.
-f flag stands for file, and will list file-type and uuid
```
lsblk -f
```

To check the uuid of the logical-volume/disks
```
blkid
```

To check filesystem / type / size / mounted-on
```
df -Th
```

shows all the mounted system on the machine 
```
mount -l
```

To create a new partition, Note: fdisk can only manage up to 2tb
```
fdisk /dev/[disknamehere]
```

To create a new partition using gdisk which is newer method compared to fdisk, Can handle more than 2Tb

```
gdisk /dev/[disknamehere]
```

makes a ext4 format file system.
NOTE: When configurining a lvm, you must choose a file system that is compitable.
```
mkfs.ext4 /dev/[disknamehere]
```


<h3> Types of file systems.</h3>
Xfs XFS can be helpful where large files are involved: huge data storages, large-scale scientific or bloody enterprise projects, etc.
Xt2
Xt3 
Xt4 Despite some capacity limitations, EXT4 makes it a very reliable and robust system to work with
Ufs
Exfat
Ntfs


<h3> Physical-Volume </h3>

To display the current Physical volumes
```
pvdisplay
```
To create a Physical Volume
```
pvcreate /dev/partition-name
```



<h3> Volume-Group </h3>

To display the current Volume groups
```
vgdisplay
```
To create a Volume group

```
vgcreate vgname /dev/partition-name
```


<h3> Logical-Volume </h3>

To display current Logical Volume
```
lvdisplay
```

To create a Logical volume 
```
lvcreate -L 2G -n lvname/vgname  
```

If you want to resuze the logical volume after creation you can use the lvresize command, resize command allows you to decrease and increase the size 

```
lvresize --size +1G /dev/volume/logical
```

Extend is smillar to resize, but it only allows the increase of volume.
```
lvextend -r -L +2G /dev/volume/logical
```

lvremove

To remove the logical volume
```
lvremove /dev/volume/logical
```
