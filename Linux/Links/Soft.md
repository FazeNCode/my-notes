<h2> SOFT-LINKS: </h2>	


What is a Symbolic link
A Symbolic Link, also known as Soft Link,  
In simple terms Soft-link point to a path. Think of it as a shortcut, exactly how web browser icon on your desktop is a shortcut, to the actual path.
In simple terms, it's creating a shortcut to a specfic file path using the it's own inode and data blocks.

How to create a Symoblic link

To create the symlink
```
ln -s /origin/path/file/or/folder softlink-name
```

Key-Notes:
soft-links can be used on FILES and FOLDERS.
soft-links can be used on different file systems.
permissions to a soft-link do not matter, unlike hard-link

soft-links point to a path. Think of it as a shortcut, exactly how browsers are shortcuts, to the actual path.

File System E.G: xfs, xt2, xt3 ,xt4, ufs, exfat, ntfs
