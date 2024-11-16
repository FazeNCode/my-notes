<h2> How to automatically start up VMware work station </h2>
-------------------------------------------------------------


1) Open up a notepad and paste the script. Save the file as .bat extension

<b> Side-Note: </b> Your path may difffer, your VMware folder and files might be on C: drive instead on D: drive. Configure according to your set path.

<br>

```
@echo off
start "" "D:\Program Files (x86)\VMware\VMware Workstation\vmware.exe" -x "D:\Documents\Virtual Machines\VMware ESXi 6.5\VMware ESXi 6.vmx"
```

<br>

2) Once the notepad has been saved to a .bat extention. Press Windows button and R on your keyboard, this will open up run, paste the below. 


```
shell:startup 
```

<br>

4) When running shell:startup it will take you to the startup directory in your windows machine, Copy your batch script into the path.
C:\Users\faisa\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup

<br>




Start-Process "D:\Program Files (x86)\VMware\VMware Workstation\vmware.exe" -ArgumentList "-x", "D:\Documents\Virtual Machines\VMware ESXi 6.5\VMware ESXi 6.vmx"


Side-notes:
----------

.bat extension is short for batch file. Batch files are an older method of automating tasks on windows systems


