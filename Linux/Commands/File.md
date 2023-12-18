  <h2> Create Files: </h2>


  ### Create Files:

Create a hidden file, put a . before the file name:

```bash
touch .filename.txt
```
Create multiple files, in this scenario, we create 10 files

  ```bash
touch filename{1..10}
```


```
 Create a hidden file, put a . before the file name
```
touch .filename.txt
```
  Create multiple files, in this scenario, we create 10 files
```  
touch filename{1..10}
```
Creates 100 files with the name filename1-3 
```
touch filename {file1,file2,file3} {1..100} {a..z}
 ```
Create a file with a dash
```
touch -- -filename
 ```

 <h2> Remove Files: </h2>
Remove file with a dash
```
rm -rf -- -filename	
```

Remove all file except file1
```
rm -rf !(file1)		
```


 <h2> Display Files: </h2>

To display the content inside the file, cat is short for "concatenate and print", you can also use cat to redirect input and out from the console to a file.

```
cat filename	
```

To content inside the file use the cat command followed by the arrow symbol, A redirect operator. 
! NOTE: A single ">" overides the existing file !
```
cat > filename.txt
```

To content inside the file use the cat command followed by two arrow symbol, A redirect operator. 
! NOTE: A double ">>" does not overide the existing file content, instead adds towards it. !
```
cat >> filename	
```

Stat command will display detailed information about the specific file, such as inode, creation date, permissions, etc..
```
stat /path/of/file
```


 <h2> Copy Files: </h2>

Copy a file [-r] flag is for recursive, meaning copy everything I target. -a flag keeps the attributes of the file or directory, such as the timestap, permissions.
```
cp -r -a  /src/file /destination/file .
```

Copy files from a remote machine (Linux) to a local machine (Windows), [-r] recursive  [-v] verbose
```
scp -rv faze@192.168.204.106:/home/faze/file C:\Users\Faisa\Desktop
```

Stat command will display detailed information about the specific file, such as inode, creation date, permissions, etc..
```
stat /path/of/file
```


