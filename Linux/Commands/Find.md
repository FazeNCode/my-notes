Find Name:
find /folder/ -name text.txt
will look for a file in the /folder/ with the name text.txt
find  . -name documents -type f
will look for an file that's named documents in the current directory 
find -name "f*" -o -size 512k 
find files with the name f OR 512 Kilobytes
find / -type f -name "html.txt"
find files in / -type: file -name: “html.txt” 
find -not -name "f*"
will return a list of files that don't begin with f

find /home/usersdata/ -type -f -user mariyam -exec cp –parents {} /media \;

Find Modified Minutes:
find -mmin -5 
will find all files modified in the last 5 minutes
find -mmin +5
will list all files modified before 5 minutes 
find . -cmin -5
find files in my current directory permissions changed in the last 5 minutes  . for current directory 
find -mtime  2
lists modified in the 24-hour periods.
