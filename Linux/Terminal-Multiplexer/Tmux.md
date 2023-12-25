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




Creating New Window / navigate
Window is when you are inside tmux 

[CTRL + B]  [c]
To create a new window
CTRL + B]  [SHIFT+7]
To kill the window
[CTRL + B]  [,]
To rename the window
[CTRL + B]  [w]
To choose a window, with list format


[CTRL + B]  [ALT+ARROW-UP]
To resize the window 
[CTRL + B]  [ALT+1]
To switch to even-horizontal layout 
[CTRL + B]  [ALT+2]
To switch to even-vertical layout 
[CTRL + B]  [ SHIFT+{  ]
To move the pane left 

[CTRL + B]  [q]
To view the pane numbers

[CTRL + B]  [0]
To navigate through different windows, 
NOTE:the first window starts from 0
Next to the window-name an astrish * is present indicating the current window.

COMMANDS:
tmux ls
Display tmux process running in the background
tmux new -s [session-name]
Create a new tmux session process
tmux kill-session -t [session-name]
Kill the session that is provided.
tmux attach -t [session-number]
Re-Open closed session 
tmux rename-session -t  [currentname] newname 
Rename session name, 





