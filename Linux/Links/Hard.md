HARD-LINKS:		 
ln  /origin/path/file hardlink-name
To create the symbolic link
rm -i hardlink_name
To remove the symbolic link
stat /folder/filename.jpg
To check the inode number and number of links, date of file creation etc..

Key-Notes:
hard-links can only be used on files NOT folders.
hard links can only exist on files that have the same file system.

To completely remove a hard-link, it must be deleted from all users that have the hard-link associated to the inode number
