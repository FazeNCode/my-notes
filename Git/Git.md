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

Clones a remote repository to your local machine
```
git clone https://github.com/F-Z-C/s3_test 
```


<h2> Configuring git user: </h2>

Shows a list of settings that are conifurerd to the system such as, the username, email, remote repository View the configured user on the system 
```
git config --list
```


Config git to a user which is F-Z-C
```
git config --global user.name F-Z-C
```



Config git to a user-email which is faisal_Chaudhry235@hotmail.ca
```
git config --global user.email faisal_Chaudhry235@hotmail.ca
```


Remove the configured email 
```
git config --global  --unset user.email	  |  user.name
```


Configure your remote repository to your local repository
```
git remote add origin https://github.com/F-Z-C/repo-name
```

Remove the configured git remote repository
```
git remote remove origin https://github.com/F-Z-C/repo-name
```

Configure remote repository to local repository, with github auth key
```
git remote set-url origin https://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@github.com/FazeNCode/rhelproj
```

