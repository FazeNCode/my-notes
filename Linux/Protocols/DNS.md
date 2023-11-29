Domain Name System:
Forward Lookup Zones:
Forward Zones in a Domain Name System are used to map hostname to an I.P address.
nslookup  www.google.com   (Referred to as forward query lookup)

Reverse Lookup Zones:
Reverse Zones in a Domain Name System are used to map I.P addresses to hostname.
nslookup  142.251.33.174   (Referred to as a reverse query lookup)

DNS-zone also known as (zone of authority). A portion of the dns tree that covers one domain name or child domain name.

Domain Name Systems
Contain all the records mentioned below

NS  (NameServer Record)
NS-Record 


A Record 
A Record is referred to as host record, which contains the ipv4-addresses 

PTR  (Pointer Record) 
Used for reverse DNS lookups. It associates an IP address with a domain name, allowing the resolution of an IP address to a hostname.  

Glue A Record
A record that maps the name of NS record to an ip addresses 




SOA  (Start of Authority Record)
Contains important information about the domain, such as  the primary DNS server, the email of the domain administrator, domains serial number, and timers for refreshing

CNAME  (Canonical)  
A CNAME is a type of DNS record that maps one domain name to another domain. It is often used to create aliases for existing hostnames.
For example, “www.fazencode.com”, to “fazencode.com”.
the name of the mail server is often aliased to mail or SMTP and the name of a web server to www.

MX  (Mail Exchange)  
The mx record points to an SMTP server, when you send an email to another domain then your mail

Simple Mail Transfer Protocol 
Port-#:	 25, 587(Secure)   • For Sending  • Relies on TCP
