<h2> Upgrading ESXi Host v6.7 To v7 Z</h2> 
<br>
Step 1: Download the offline bundle, from the official 
https://customerconnect.vmware.com/downloads/details?downloadGroup=ESXI700&productId=974&rPId=112135

<br>
Step 2: Upload the offline bundle into your datastore1, ISO folder.
<b> NOTE: Upload the entire zip archive </b>

<br>
Step 2.1: Log into the ESXi through SSH. 
NOTE: enable ssh in ESXi host web if it's not enabled.

<br>
Step 3: The command below will verify which versions are available 
esxcli software sources profile list -d "/vmfs/volumes/datastore1/ISO's/VMware-ESXi-7.0U3n-21930508-depot.zip"

<br>
Step 4: 
esxcli software profile install -p ESXi-7.0U3n-21930508-standard -d "/vmfs/volumes/datastore1/ISO's/VMware-ESXi-7.0U3n-21930508-depot.zip"


