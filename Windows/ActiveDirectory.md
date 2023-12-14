Active Directory: (Windows)
LDAP & Radius: (Linux / MacOs)

What is Active Directory (AD) ?
Directory service developed by Microsoft, which is a database and set of services which connects users with network resources.  
For example, When you use, or have used a computer in elemntry or highschool school, the credentials for you to login to the computer are configured in Active Directory, such as username password, permissions, etc.. 

What does it do ?
- AD stores information related to objects such Computers, Users, Printers, etc..


How does it work ?
- Authenticates users and devices using Kerberos tickets.
- Non-Windows devices such as Linux, MacOS, firewalls, etc.. can also
  authenticate to Active Directory via LDAP or RADIUS


LDAP:
- Lightweight Directory Access Protocol is used for authentication, whether it's users,
  or devices 


RADIUS: 
- Remote Authentication Dial-In User Service is a protocol that also allows authentication
  wether it's users or devices.
- RADIUS is a network access server (NAS), such as a VPN, router, switch.


::Physical Active Directory Components::
- Domain Controller
- AD DS

Domain Controller:
- Main component for Active Directroy.
- Kerberos ticketing authentication.
- Provides authentication and authorization services.
- Allow administrative access to manage user accounts and network resources.
- Replicates updates to other domain controllers in the domain and forest.

Active Directory Data Store:
- Consists of the Ntds.dit file. Contains all users, objects, groups, hashed passwords.
- Stored by default in the %SystemRoot%\NTDS folder on all domain controllers.
- Accessible only through the domain controller processess and protocols.


::Logical AD Components::
- AD DS Schema
- Domains
- Trees
- Forests
- OU
- Truts
- Objects

Active Directory Data Store Schema:
- Defines every type of object that can be stored in the directory
- enforces rules regarding object creating and configuration.

Domains: 
- Domains are used to group and manage objects in organization 
- An administrative boundary for applying policies to groups of objects.
- A replication boundary for replicating data between domain controllers

Trees: 
- Domain tree is a hiearchy of domains in AD DS
- Share a contigous namespace with the parent domain
- Can have additional child domains
- By default create a two-way transitive trust with other domains


Forests:
- Share a common schema 
- Share a common configuration partition
- Share a common global catalog to enable searching
- Enable trusts between all domains in the forest


Organizational Units:
- Represent your orgination hiearchically and logically
- Manage a collection of objects in a consistent way
- Delegate permissions to administer group of objects
- Apply policies

Truts:
- Provide a mechanism for users to gain access to resources in another domain
- Directional, flows from trusting domain to the trusted domain.
- Transitive, realtionship is extended beyond two-domain to other trusted domains.

Objects: 
- Users
- InetOrgPerson
- Contacts
- Groups
- Computers
- Printers
- Shared folders


--- BreakDown---
Domains are used to group and manage objects in an organization 

Multiple Domains, are referred to as Trees, which consists of parent domain and children domain.

Multiple Trees, are referred to as Forests, inside the Forests are called OU


Orginzational Units consists of Objects 


Trusts is across forests or cross domains 


