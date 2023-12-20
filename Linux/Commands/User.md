<h2> Display User: </h2> 


Display the users on the machine, along with their UID, GID and shell 
```
cat /etc/passwd
```

```
compgen -u
```
Display the details of the active user.
```
id user_name
```
Display the last login users
```
last
```
Display who’s logged into the system
```
who
```
Check what group has sudo power
```
getent group sudo 
```

1. The username
2. Password status Locked (L), No Password (NP), Password (P)
3. Date of last password change
4. Minimum password age
5. Maximum password age
6. Warning period  (days given before password expires.)
7. Inactivity period (days after a password expires before it is locked.)
```
passwd -S user_name
```
Check the users password settings
```
chage -l user_name  
```
Set the expiration date for a user 
```
chage -E 2023-01-30 user_name
```
Password will expire after a maximum of 30 days 
```
chage -M 30 user_name
```
Minimum amount of days the user can his/her password
```
chage -m 7 user_name
```
Remove the password expiration date
```
chage -M -1 user_name
```

<!--- 
# ps -aux |grep [username] 
# List the process on a user
pkill -f [proccess-name]
Kill a process with the process name
killall -TERM -u [username]
Kill the process on a user
--->


 <h2> *<ins>Adding User:</ins>** </h2>
 
Create a user with a non-interactive shell
```
adduser user_name -s /sbin/nologin 
```

Create a user with the bash shell. the -s flag stands for shell
```
adduser user_name -s /bin/bash  
```

Create a user with 1100 uuid
```
sudo user_add -u 1100 user_name
```

Create a user with a home directory  
```
sudo useradd m user_name
```

Create a user with a system account, system account does not have a /home directory, usually daemons use system account.
```
sudo useradd  --system user_name
```

Create a user with the username john and password will be 12345.
```
echo -e “john” | passwd --stdin “12345”
```


<h2> *<ins>Deleting User:</ins>** </h2>

Remove the user named username from the group sudo.
```
sudo userdel user_name sudo
```

The -f would forcefully remove this user, including the user’s home directory/mail (if any) 
```
userdel -rf user_name
```