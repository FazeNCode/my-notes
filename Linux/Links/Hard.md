<h2> HARD-LINKS: </h2>

<h2> What is a Hard link? </h2>
<br>
A hard link is a mechanism in file systems that allows associating multiple entries (filenames) with the same underlying data blocks on disk.
Essentially, it creates additional references to an existing inode, which contains information about a file. In simple terms, it's creating a shortcut to a specfic file path of your choice, making it eaiser to access by just Hard link name.

All hard links to a file share the same inode, and changes made to any of the hard links are reflected in all other hard links, as they point to the same data.


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

Some file type examples: xfs, xt2 exFAT, ntfs etc...

To completely remove a hard-link, it must be deleted from all users that have the hard-link associated to the inode number





