
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

To create a new partition 
```
fdisk /dev/[disknamehere]
```

To create a new partition using gdisk which is newer
Can handle more than 2Tb
```
gdisk /dev/[disknamehere]
```

makes a ext4 format file system.
```
mkfs.ext4 /dev/[disknamehere]
```




Physical-Volume

```
pvdisplay
```

To display the current Physical volumes
pvcreate /dev/partition-name
To create a Physical Volume


Volume-Group

```
vgdisplay
```
To display the current Volume groups
vgcreate vgname /dev/partition-name
To create a Volume group


Logical-Volume

```
lvdisplay
```


To display current Logical Volume
lvcreate -L 2G -n lvname/vgname  
To create a Logical volume 
lvresize --size 1G /dev/volume/logical
To resize the logical volume
lvextend -r -L +2G /dev/volume/logical
To extend the logical volume 
lvremove /dev/volume/logical
To remove the logical volume


