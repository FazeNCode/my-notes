Upgrading ESXi Host v6.7 To v7
	
Step 1: Download the offline bundle
https://customerconnect.vmware.com/downloads/details?downloadGroup=ESXI70U3N&productId=974&rPId=46384

Step 2: Upload the offline bundle into your datastore1, ISO folder.
NOTE: Upload the entire zip archive

Step 2.1: Log into the ESXi through SSH. 
NOTE: enable ssh in ESXi host web if it's not enabled.

Step 3: The command below will verify which versions are available 
esxcli software sources profile list -d "/vmfs/volumes/datastore1/ISO's/VMware-ESXi-7.0U3n-21930508-depot.zip"

This is the root directory for the VMFS file system. VMFS is a clustered file system that VMware uses to store virtual machine files, such as virtual machine disk files (VMDKs). 


Step 4: 
esxcli software profile install -p ESXi-7.0U3n-21930508-standard -d "/vmfs/volumes/datastore1/ISO's/VMware-ESXi-7.0U3n-21930508-depot.zip"

This is a subdirectory within the VMFS root directory. It is where individual datastores (storage volumes) are mounted. Each mounted volume represents a datastore where virtual machines and other files can be stored.
