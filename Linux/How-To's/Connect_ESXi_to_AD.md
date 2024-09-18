<h3> How To Connect ESXi Host version 7 to Active directory </h3>

Why is connecting ESXI to an Active directory beneficial?
<br>
Grant any specific user's with certain permissions to access ESXi configuration management.
For example if a user named "Christy" job involves her to manage Virtual machines and Data Store, we can specifically grant access to those specified categories based on her work load. This tightens the security measures.

<br>
<br>
---- PART-1 Adding "Roles and Features" (Active Direocty | DNS) ----
<br>
Step 1 
In Windows Server, open up Server Manager Dashboard 
- Click on "Manage" next to "Tools"
  - Click on "Add Roles and Features" 

<br>
<br>
<img src="https://raw.githubusercontent.com/FazeNCode/Images-Repository/main/Virtualization/VmWare/ESXi/ServerManager_(1).png" alt="Open Server Manager" />


<br>
<br>
Step 2: "Before you Begin" 
<br>
- Click Next

<img src="https://github.com/FazeNCode/Images-Repository/blob/main/Virtualization/VmWare/ESXi/ServerManager_(10).png" alt="Open Server Manager" />

Step 3: "Installation Type"
<br>
- Select "Role based or feature-based installation"
  - Click "Next"

Step 4: "Server Selection"
<br>
- Select "Select a server from the server pool"
  - Select "Your windows server name".  NOTE: This can be changed to the desired name.

Step 5: "Server Roles"
- Select "Active Directory Domain Services"
  - Click Add Feature
- Select "DNS Server"
  - Click Add Feature. NOTE: WE CAN CHANGE THE I.P TO A STATIC IP SO THERE WON'T BE ANY CONFLICT WITH DHCP
- Click "Next"


"Features"
- Click Next

"AD DS"
- Click Next


"DNS Server"
- Click Next

"Confirmation"
- Click Install


"Results" 
Click on Promote this server to a domain controller



<br>
<br> 

---- PART-2 (PROMOTING DOMAIN CONTROLLER) ----

"Deployment Configuration" (Image-1)

"Domain Controller Options" (Image-2)
- Select Domain name system
- Select Global Catalog 
The two above should already be selected by default, but in case they are not, make sure to select them
- Enter a password


"DNS Options" (Image-3)
- Click Next


"Additional Options" (Image-4)
- Leave the NetBIOS name default if there is no need to change it.
- Click next


"Paths" (Image-5)
- Click Next


"Review Options" (Image-7)
- Click Next


"Prerequisites Check"  (Image-8)
With all the pre-configured steps we've done in part 1 we should be in the clear to click install
- Click Install
Once completed you will be signed out and the windows server will reboot automatically.
Once the reboot has been completed you will notice your username to login has been updated.

<br>

---- SHOW-CASE OF PROMOTED DOMAIN CONTROLLER ----

ActiveDirectory Configured (Image-10)
- In ServerManager click on tools
- Inside tools drop down menu click on Active Users and Computers. 


Active users and Computers (Domain)
- Inside you'll notice the domain we had configured, in the earlier steps, specifically in the Promoting Domain Controller setup wizard. 
Image REF: C:\Users\Faisa\Desktop\ESXi_Part2 Promote_DomainController_(1) 


Active users and Computers (Computers)
- Inside Computers you'll notice there are no computers, that's because we have not configured our ESXi host to our domain controller. In order to connect we must move on to configuring our ESXi


Active users and Computers (Domain Controller)
- Inside the Computers Directory you will see the default users and the default security groups.
in later steps we'll create our user and security group

Active users and Computers (Users)
- Inside the Computers Directory you will see the default users and the default security groups.
in later steps we will create our user and security group


<br>
<br> 

---- PART-3 CONFIG FORWARD & REVERSE LOOKUP ZONES ----

Folder path: ESXi_Part3

<br>
==== Pre-configuration DNS SETUP (OPTIONAL) ==== 
<br>

Before Configuring DNS records, it's recommended to configure a static IP Address instead of DHCP, this is so there is no potential conflict in the later steps.

In Server Manager under Dashboard, 
- Click Local Server	 Image: Pre_DNS_conifuration(0.1)
 Inside of Local Server properties, 
- Click on Ethernet0 

Inside Network connections,
- Right click Ethernet0
- Click Properties  	 Image: Pre_DNS_conifuration(0.2)

Inside Ethernet0 properties
- Click on TCP/IPv4 	 Image: Pre_DNS_conifurationIPv4(0.3)


Inside Internet Protocol Version 4 (TCP/IPv4) Properties 
- Click on "Use the following IP address: 	Image: Pre_DNS_conifurationIPv4(0.3)
- Input your desired static I.P address
- If you are not sure about your network information, use the ipconfig command in the cmd.
 In my example I changed my I.P Address last octet from 192.168.244.141 >> 192.168.244.142
You can also input 192.168.244.141 as your static I.P Address in TCP/IPV4 Properties, it's personal preference 

Once Configured
- Click OK 


Step 1:
=== DNS Record SETUP ===
- Click on tools in Server Manager.
- Click "DNS" in the Tools drop down menu.


Step 2: 
=== Inside DNS Manager ===
- Click on "DNS"
- Click on the arrow beside your computer name to expand.


Step 3:
=== Reverse Lookup Zone Wizard SETUP ====
- Right Click on "Reverse Lookup Zones"  & click "New Zone"
 - "Click Next"
 - "Zone Type" 				    	(Leave Default & Click Next)
 - "Active Directory Zone Replication Scope" 	(Leave Default & Click Next)
 - "Reverse Lookup Zone Name" 		     	(Leave Default & Click Next)
 - "Reverse Lookup Zone Name" (Enter first 3 octet of your I.P Address) E.G 192.168.244
 - "Dynamic Updat:" 				(Leave Default & Click Next)
 - "Completing New Zone wizard" 		(Click Finish)


Step 4:
=== Forward Lookup Zone Wizard SETUP ===
- Click and expand Forward Lookup Zones
- Click on your Domain Controller. for example mine is "WindowServ.local"
- Right Click inside & Select "New Host (A or AAAA)"
- Give a suitable hostname of your choice.
- Give a suitable IP address associated.
- Check PTR Record

  Inside Forward Lookup zone right click


<br>
<br> 

---- PART-4 CONFIGURE DNS SETTINGS FOR ESXi Host ----
Folder path for images: ESXi_Part4


Step 1: In the ESXi press F2 on keyboard to edit settings,
Step 2: Highlight and press Enter on "Configure Management Network" 
Step 3: Edit "DNS Configuration" settings
 - Primary DNS Server:
   - I.P Address of domain controller (Window Server)

 - Alternative DNS Server: 
   - Leave empty

 - Hostname:
   - Enter the hostname created in Step 4, Forward Lookup zone
  
Step 4: Edit "Custom DNS Suffixes"
 - Enter localdomain, Domain Controller, FQDN

Step 5: Once all configured, press "ESC" on the keyboard and apply the changes.

Step 6: Highlight and press Enter on "Restart Management Network" 
 - Enter F11 on keyboard to click OK

Step 7: "Highlight and press Enter on "Test Management Network"
 - Ping Address #0: Enter Default gateway I.P
 - Ping Address #1: Enter I.P of Domain controller (Window Server)
 - Resolve Hostname: Enter Hostname configured in Forward Lookup Zone step.

<br>

-------------- PART-5 ENABLE SETTINGS IN ESXi WEB CONSOLE --------------
Step 1: In the ESXi host enable the following services DCUI, TSM-SSH, Active Directory all
[Manage]
Services:
- DCUI
- TSM-SSH

Step 2: Under networking Networking in the ESXi Host navigate to [Firewall Rules]
Enable Active Directory all

Step 3: In ESXi Host, go to time & date settings, configure NTP server.
- Manage
  - Time & Date
  - IP of domain controller 
	- 192.168.244.140

<br>

-------------- PART-6 CONNECT TO DOMAIN CONTROLLER --------------
Step 1: In ESXi Host, go to Authentication and Join domain
- Manage
  - Authentication
  - Join domain
    - Domain name: win.local
    - User Name: Administrator


<br>

IMPORTANT: Before moving onto PART-7
<br>
In Active Drirectory Users and Computers
 - Right click: on Domain Controller
   - Create group
   - Group Name: ESX Admins
   
<br>

-------------- PART-7 ADD ADDITIONAL AD USERS TO ESXi --------------
Step 7: In ESXi Host, under Host settings add the specified user or group.
Click:  
- Host
  - Actions, with the gear symbol
  - Permissions
   - Add user
     - faze@win.local
     - win.local\group-name
