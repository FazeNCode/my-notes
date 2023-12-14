
What is strace used for?
Strace is used for system calls. 

What is a system call? 
A system call is a fundamental interface between an application program and the underlying kernel of an operating system.
For example every input you do in the computer is considered a system call,


strace ./write_file

strace -o output_file.txt ./write_file
The command above will output the system call for ./write_file which is a c file
to the output_file.txt


strace -e trace='write' ./write_file
Call a specific system call, instead of showing all system calls


STRACE DOES NOT TRACE CHILD PROCCESS BY DEFAULT

strace -f ./write_file


strace -c -w ls
Displays syscalls, Number of calls, Erros, etc..
-c flag stands for count

strace -P /etc/resolv.conf dig yahoo.com

strace -e trace=socket dig yahoo.com
