<h3> WSL </h3>

<p> What is WSL?</p>
WSL is short for Windows Subsystem for Linux, allows users to run Linux based distribution on windows machines.


To view the current distribution installed/configurerd on the machine.
```
wsl -l -v
```

List the version of the running WSL on your system.
```
wsl --version 
```

Will set the default version of wsl to 2

```
wsl --set-default-version 2
```

List the avialble distors that can be installed on your machine 
```
wsl --list --online
```

Install the distrobution you would like to install 
-d flag stands for distribution

```
wsl --install -d [distro-name]

```



