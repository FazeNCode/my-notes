<h2> Upgrading ESXi Host v6.7 To v7 Z</h2> 

Step 1: Download the offline bundle
https://customerconnect.vmware.com/downloads/details?downloadGroup=ESXI700&productId=974&rPId=112135

Step 2: Upload the offline bundle into your datastore1, ISO folder.
NOTE: Upload the entire zip archive

Step 2.1: Log into the ESXi through SSH. 
NOTE: enable ssh in ESXi host web if it's not enabled.


Step 3: The command below will verify which versions are available 
esxcli software sources profile list -d "/vmfs/volumes/datastore1/ISO's/VMware-ESXi-7.0U3n-21930508-depot.zip"


Step 4: 
esxcli software profile install -p ESXi-7.0U3n-21930508-standard -d "/vmfs/volumes/datastore1/ISO's/VMware-ESXi-7.0U3n-21930508-depot.zip"


ESXI Hypervisor 7 installer
https://customerconnect.vmware.com/downloads/details?downloadGroup=ESXI70U3N&productId=974&rPId=46384
