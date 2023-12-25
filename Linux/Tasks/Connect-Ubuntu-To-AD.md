What is SSSD?
System Security Services Daemon 
Provides access on a client system to remote idenity and authentication providers.

What is adcli?
adcli is a tool whcih allows the admin to join the local machine to an ctive directory, it's role is to create the computer account on the domain and adjuct the Kerberos (keytab configruation).

What is keytab?
keytab is a file containing pairs of Kerberos prinicaps and encrypted keys (which are derived from the Kerberos password)

-------------------------------------------------------------------------------------------------------
-- Setup Active Directory Domain Services Configration Wizrd On Windows-Server --
Select the deployment operation:
Check: Add a new forest
Root domain name: Windows1.local
password: 123456me!!
The NetBIOS domain name: Winds  [The NetBIOS domain name is used on windows main screen]
--------------------------------------------------------------------------------------------------------
-- Joining Ubuntu To Active Directory using SSSD ---

Step 1: Install services & put the windows I.P address as the dns in the ubuntu server, in network config
apt install sssd-ad sssd-tools realmd adcli 

Step 1.1: Check the group plolicies
apt policy sssd-ad sssd-tools realmd adcli

Step 1.2 Put the nameserver and ip address of windows machine in /etc/resolv.conf
vi /etc/resolv.conf

Step 2: Confirm that the Ubuntu machine is able to resolve Active-Driectory domain
realm discover WIN-Server1

Step 3: Join the Ubuntu server with windows server, using -User flag to join with Administrator user
realm join WIN-Server1 -U Administrator

Step 4: To Confirm the setup has been completed check the sssd.conf file
cat /etc/sssd/sssd.conf   [Configuraion file for, System Security Service Daemon]
cat /usr/share/pam-configs/mkhomedir   [In this file you can give the user a home directory on creation]

Step 5: To make a home directory for the user. PAM (Pluggable Authentication Module) a framework that provides system administrators with the ability to incorporate multiple authentication mechanisms into an existing system.
pam-auth-update --enable mkhomedir

Step 6: !IMPORTANT! Must permit the specified user to login.
realm permit username@windows.local

Step 6.1: To give sudo permission to a AD user edit the sudoers file and paste the below
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


-------------------------------------------------------------------------------------------------
-- CIFS Mount Ubuntu server with Windows Server --

Step 1: Install the necessary packages.
apt install cifs-utils samba samba-client libnss-winbind winbind
Packages such samba, samba-client libnss-winbind winbind are used for more extensive intergration with Samba and Active Directory, such user authentication, user mapping.

Step 2: Create a folder to mount
mkdir /media/mount

Step 3: Create a folder on the windows machine 
Right click folder >> Properties >> Advance Sharing
Check mark: Share this folder
Click on >> Permissions >> Check mark: Full Control
Once Configured, the Network Path will be updated, which is used for mounting on the Linux machine.

Step 4: Edit the /etc/nsswitch.conf file, to put "wins" before dns
nano /etc/nsswitch.conf
hosts: files mdns_minimal [NOTFOUND=return] wins dns

Step 5: Make a credentials file on the specified user account, example listed below:
vi /home/david/.smbcred
username=david@win.local
password=123456me!!
domain=wins.local

Step 6: Edit the fstab file
First:  Windows machine name and the directory which we are going to mount to.
Second: Mount path on the linux machine
Third:  File sharing method
Fourth: Credential file path
Fifth:  Group ID / User ID 
Sixth:  Permissions on the on file and directory

vi /etc/fstab
//WINDOWSERVER/Mounted /media/mount cifs credentials=/home/ads@win.local/.smbcred,gid=966660001,uid=9666600001,file_mode=0777,dir_mode=0777 0 0

vi /etc/fstab
//cubisdata/cds /mnt/test-mount cifs	 rw,vers3.0,credentials=/etc/smbount.ea_linux_admin2,uid=15099,gid=15099,file_mode=0775,dir_mode=0775 0 0

----------------------------------------------------------------------------------------------
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
-------------------------------------------------------------------------------------------

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

---------------------------------------------------------------------