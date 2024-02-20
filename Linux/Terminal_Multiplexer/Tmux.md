TMUX:


What is Tmux? 
It allows the user the ability to have a split screen terminal session, side-by-side
Also preserving the state, if the user loses connection.

NOTE: Tmux sessions are saved on the user that's being used, NOT ALL USERS!


sudo yum install tmux -y

Creating New Session / navigate 
Session is what you create to start using tmux

[CTRL + B] [%]
To create a new session on side
[CTRL + B]  [SHIFT + "]
To create a new session on bottom 
[CTRL + D] 
To delete the session
[CTRL + B]  [SHIFT+4]
To rename tmux session

[CTRL + B]  [>] 	[CTRL + B]  [<]  
To move the cursor to the right or left terminal 




<h2> Creating New Window / navigate </h2>
Window is when you are inside tmux 
To create a new window type CTRL + B then let go of CTRL + B and type c on keyboard
```
[CTRL + B] + [c]
```

To kill the window
```
[CTRL + B] + [SHIFT+7]
```
To rename the window
```
[CTRL + B] + [,]
```

To choose a window, with list format
```
[CTRL + B] + [w]
```


To resize the window 
```
[CTRL + B]  [ALT+ARROW-UP]
```

To switch to even-horizontal layout 
```
[CTRL + B]  [ALT+1]
```

To switch to even-vertical layout 
```
[CTRL + B]  [ALT+2]
```

To move the pane left 
```
[CTRL + B]  [ SHIFT+{  ]
```


To view the pane numbers
```
[CTRL + B]  [q]
```


To navigate through different windows, 
NOTE:the first window starts from 0
Next to the window-name an astrish * is present indicating the current window.
```
[CTRL + B]  [0]
```



<h4> COMMANDS </h4>
Display tmux process running in the background
```
tmux ls
```

Create a new tmux session process
```
tmux new -s name-the-session
```

Kill the session that is provided.
```
tmux kill-session -t name-the-session
```

Re-Open closed session 
```
tmux attach -t name-of-session
```

Rename session name
```
tmux rename-session -t name-of-session new-session-name
```






