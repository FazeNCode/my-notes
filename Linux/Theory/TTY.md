TTY
TeleTypeWriter (TeleType)

CTRL + ALT + F2
Opens up another terminal session, this is usefull when you want to have multiple sessions without installing terminal multiplexer like tmux or screen.

Run the command below to display which tty you are currently in.
```
tty
```

<br>

Users can open multiple terminal sessions, for example you can use F3, F4, F5.. and so on, to utilize multiple sessions

Switching to the different terminal session, is same key-binding as starting new terminal session.

<br>


GETTY
Get Terminal Type is an essesntial program in all linux distrobutions. 
<br>
To stop the terminal service run the command above
```
systemctl stop getty@tty2.service
```



The source command is used to refresh or reload the bash configuration for the current shell.
```
source ~/.bashrc
```


yes command is used to output multiple pieces of text into a file, usually used in scripts.
```
yes "some-text" | head -n 200 >> file.txt
```

