<h2> SOFT-LINKS: </h2>	


What is a Symbolic link
A Symbolic Link, also known as Soft Link,  
A symbolic link, often referred to as a symlink or soft link, is a special type of file in a file system that acts as a reference or pointer to another file or directory. Symbolic links are used to create shortcuts or aliases to existing files or directories, allowing you to access them from different locations in the file system.
Think of it as a shortcut, similar to how web browser icon on your desktop is a shortcut, to the actual path.

Note: Symbolic link creates it's own inode number and data blocks when it's created. This is a key-point, as this is one of the differences between Symbolic link from a Hard link 

<h2> How to create a Symoblic link? </h2>
To create the symlink
```
ln -s /origin/path/file/or/folder softlink-name
```

<h2> What Now? </h2>
You have successfully created a Symbolic link, now when you "ls -al" to list all, you will see a link name beside the file or folder 

To remove the Symbolic Link use "rm" command, -i = interactive
```
rm -i Symbolic_name
```

Key-Notes:
soft-links can be used on FILES and FOLDERS.
soft-links can be used on different file systems.
permissions to a soft-link do not matter, unlike hard-link

File System E.G: xfs, xt2, xt3 ,xt4, ufs, exfat, ntfs

<br>
<br>

<h2> HARD-LINKS: </h2>

<h2> What is a Hard link? </h2>
<br>
A hard link is a mechanism in file systems that allows associating multiple entries (filenames) with the same underlying data blocks on disk.
Essentially, it creates additional references to an existing inode, which contains information about a file.
In simple terms, it's creating a shortcut to a specfic file path using the file paths inode and data bolocks of your choice.

All hard links to a file, share the same inode, and changes made to any of the hard links are reflected in all other hard links, as they point to the same data.


<h2>How to create a Hard link?</h2> 
<br>
To Create Hard link, use "ln" which stands for "link" followed by the path to the file you are wanting to link, and lastly the name of the hard-link, which can be of your choice.  

```		 
ln  /origin/path/file hardlink-name
```

<h2>What now? </h2>
<br>
You have successfully created a Hard link, now when you "ls -al" to list all, you will see a link name beside the file path.

To remove the Hard Link use "rm" command, -i = interactive
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
To completely remove a hard link, it must be deleted by removing the corresponding directory entry that points to the inode

File System E.G: xfs, xt2, xt3 ,xt4, ufs, exfat, ntfs



