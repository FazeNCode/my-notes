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
Remove file with a dash
```
rm -rf -- -filename	
 ```
Remove all file except file1
```
rm -rf !(file1)		
```