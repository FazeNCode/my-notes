<h3> HARD-LINKS </h3>

What is hard link?
A hard link is a mechanism in file systems that allows associating multiple entries (filenames) with the same underlying data blocks on disk.
Essentially, it creates additional references to an existing inode, which contains information about a file.

All hard links to a file share the same inode, and changes made to any of the hard links are reflected in all other hard links, as they point to the same data.


To Create Hard link, use "ln" followed by the path to the file you are wanting to link, and lastly the name of the hard-link. This will associate a link to the specified path. 

```		 
ln  /origin/path/file hardlink-name
```
To remove the symbolic link
```
rm -i hardlink_name
```
Will display a abundant of information on a file, such as inode number,
number of links, date of file creation and much more 
```
stat /folder/filename.jpg
```

Key-Notes:
Hard-links can only be used on files NOT folders.
Hard links can only exist on files that have the same file system.

Some file type examples: xfs, xt2 exFAT, ntfs etc...

To completely remove a hard-link, it must be deleted from all users that have the hard-link associated to the inode number





