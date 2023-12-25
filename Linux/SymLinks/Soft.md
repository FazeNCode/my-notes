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


