Kerberos is network authentication protocol.
- Port 88  by Default runs on UDP

<br>
Kerberos Realm is the domain 
 - Principal (a unique identiy, can be a user or  service)

<br>
KDC: Key Distribution Center (The Heart)
- Supplies tickets and generates temporary session keys,  to securely authenticate to a service.
- KDC stores all the secret symmetric keys for users and services 
- Two servers within the KDC (Authentication server | Ticket Granting server)

<br>
TGT: Ticket Granting Ticket
Ticket needed for requesting TGS from KDC,

<br>
TGS: Ticket Granting Service

<br>
SPN: Service Principle Name
an indentifier for each service instance, key component in the process of authentication
