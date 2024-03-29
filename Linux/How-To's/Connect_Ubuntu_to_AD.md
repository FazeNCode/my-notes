



<h2> You must have already configured Active Directory, before perceeding. </h2>
<h3> <h3>
-- Setup Active Directory Domain Services Configration Wizard On Windows-Server --
Select the deployment operation:
Check: Add a new forest
Root domain name: Windows1.local
password: password
The NetBIOS domain name: Winds  [The NetBIOS domain name is used on windows main screen]


<h2> Joining Ubuntu To Active Directory using SSSD </h2>

Step 1: Install the required packages.

```
apt install sssd-ad sssd-tools realmd adcli 
```

<h3> What is SSSD? </h3>
System Security Services Daemon 
Provides access on a client system to remote idenity and authentication providers.

<h3> What is realmd </h3>
<p> Relamd allows us to use the realm commands to discover, and connect to the an existing Active Directory domain controller </p>

<h3> What is adcli? </h3>
adcli is a tool whcih allows the admin to join the local machine to an Active directory, it's role is to create the computer account on the domain and adjuct the Kerberos (keytab configruation).

<h3> What is keytab? </h3>
keytab is a file containing pairs of Kerberos prinicaps and encrypted keys (which are derived from the Kerberos password)



Step 1.1: Check the group plolicies

```
apt policy sssd-ad sssd-tools realmd adcli
```

Step 1.2 Put the nameserver and ip address of windows machine in /etc/resolv.conf

```
vi /etc/resolv.conf
```

Step 2: Use the discover command to display that the Ubuntu machine is able to resolve Active-Driectory domain

```
realm discover WIN-Server1
```

Step 3: Join the Ubuntu server with windows server, using -User flag to join with Administrator user

```
realm join WIN-Server1 -U Administrator
```

Step 4: To Confirm the setup has been completed check the sssd.conf file

[Configuraion file for, System Security Service Daemon]
```
cat /etc/sssd/sssd.conf   
```

In this file you can give the user a home directory on creation
```
cat /usr/share/pam-configs/mkhomedir  
```

Step 5: To make a home directory for the user. PAM (Pluggable Authentication Module) a framework that provides system administrators with the ability to incorporate multiple authentication mechanisms into an existing system.

```
pam-auth-update --enable mkhomedir
```

Step 6: Permit the specified user to login. NOTE: This step is important
```
realm permit username@windows.local
```

Step 6.1: To give sudo permission to a AD user edit the sudoers file on the linux machine and paste the below
visudo 
username@AD_DOMAIN ALL=(ALL:ALL) ALL

::Optional::
Step 7:To give domain administrators to have full sudo access on the machine The % specifies a group.
vi /etc/sudoers.d/domain-admin
%domain\ admins@windows.local		ALL=(ALL)	ALL

::ERROR::
If you are receving an error related to group policy, delete the gpo_cache folder
vi /var/lib/sss/gpo_cache

::ERROR::
Failed to start System Secruity Services Daemon
sssd.service Start request repeated too quickly








--- Applying Group Policy On Ubuntu server using Adsys ---

What is adsys?
adsys is the Active Directory Group policy client for ubuntu, and contains startup script.
- adsysd daemon implemnts group policy protocol. relies on Kerberos, Samba and Ldap for authentication and policy retrieval
- adsysctl is a Command line interface which controls the daemon and it'sstartup

Step 1: apt install adsys

Step 1.2: cd /desktop 
Change into the desktop, before running the adsysctl policy command, so the files get created on desktop.

Step 2: adsysctl policy admx all
Will download the files needed.

Step 3: Connect ubuntu to windows server using smb shares. 
On ubuntu open Files. Click on Other Location, and enter the below.
smb://192.168.244.159


Connect ubuntu to windows server using smb shares. 
On ubuntu open Files. Click on Other Location, and configure as shown below.
smb://192.168.244.159

--- SAMBA BASIC CONFIG FILE ---

vi /etc/samba/smb.conf
[guest]
	path = /home/faze/Shared_folder
	read only = no
#	guest ok = yes
#	guest only = yes


Adding a dedicated user for samba, for this step comment out the "guest ok" | "guest only" line in smb.conf
sudo useradd -M -s /sbin/nologin sambauser
sudo passwd sambauser
sudo smbpasswd -a sambauser
sudo systemctl restart smbd

