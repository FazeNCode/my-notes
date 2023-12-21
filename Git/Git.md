<h2> ESSENTIALS: </h2>

Displays what files and folders which need to be added to the commit stage, or to be commited

```
git status 
```

Display all the branches. Without [-a] option to show current branch
```
git branch -a
```

Creates a branch but remains in the current branch
```
git branch -M branch-name
```

Clones a remote repository to your local machine by giving the path (URL) of your repository from github 
```
git clone https://github.com/Clone/Repo 
```


<h2> Configuring git user: </h2>

Shows a list of settings that are conifurerd to the system such as, the username, email, remote repository View the configured user on the system 
```
git config --list
```


Config git to a user which is Your_Git_Username
```
git config --global user.name 
```



Config git to a user-email which is your_email@hotmail.ca
```
git config --global user.email your_email@hotmail.ca
```


Remove the configured email 
```
git config --global  --unset user.email	 
```
Remove the configured username
```
git config --global  --unset user.name
```

Configure your remote repository to your local repository
```
git remote add origin https://github.com/Your/Repository-Name
```

Remove the configured git remote repository
```
git remote remove origin https://github.com/Your/Repository-Name
```

Configure remote repository to local repository, with github auth key
```
git remote set-url origin https://ghp_WkPLvKSUCT1J0ee9Hm5k91SXDGA@github.com/FazeNCode/rhelproj
```

