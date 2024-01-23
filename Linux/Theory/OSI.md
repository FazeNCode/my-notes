<h2> OSI MODEL </h2>
TCP/IP:
7.Application;                                    	 Data;  
6.Presentation;                                   	 Data;
5.Session;                 PDU;                    	 Data;
4.Transport;            (Segments/datagram)   	    Transport;
3.Network;               (Packets)                  Internet;     
2.DataLink;               (Frame)             		LinkLayer;      
1.Physical;                (Bits)              		LinkLayer;

Data moves from one computer to another in Frames.

[Layer 1:]  Hub | Nic | Access point
Hub Creates and expands Collision and Broadcast domain. 
A group of nodes that can hear each other.
Collision occurs when two nodes send signals at the same time, if too large= traffic problems. 
 more hubs in use= larger COLLISION DOMAIN.
5. All nodes share bandwidth.

[Layer 2:]   Switch | Bridge | Nic | Access Point
 Separates Collision domain.
 Creates Broadcast domain.
 Gives every conversation full Bandwidth.
 MAC ADDRESS
 Builds a table of MAC Addresses. 
 Uses the tables to make a point-to-point connection.
 Broadcast domain is a group of nodes where they can reach      others by broadcast.
 Switch connects devices.


<h3> What do Layer 1 & 2 contain?</h3>

MAC address (Media Access Control)   The first three pairs are known as identifiers
ETHERNET 802.3 
802.11 (Wifi)
PPP-LAN, DSL-WAN, Protocols
SONET/SDH (Fibre optic backbone)



[Layer 3]  -ROUTER, Multilayer Switch Wireless Router
Separates Broadcast and Collision domain.
forwards IP packets based on the IP address. 
Routers connect networks.
Switch is used to centrally connect multiple devices on the local network and transmit data to the correct location


What does Layer 3 contain?
IPv4
IPv6
ICMP- (Internet control message protocol/PING)
ICMPv6
IPSec (Provides security to packets on layer 1-3)

Packets Delivery Scheme:
-Unicast:
-Broadcast:
-Multicast:
-Anycast:
-Geocast:
Encapsulation: Making packets. (Top to bottom)
Decapsulation: (bottom to top)

[LAYER 4]  TCP | UDP
TRANSMISSION CONTROL PROTOCOL 
Connection-oriented Protocol
Commonly used for applications that require guaranteed delivery of data, such as web browsing (HTTP and HTTPS), file transfer (FTP), and secure shell (SSH)

Works on a three way handshake.
TCP is good for internet usage because it has a validation process.

USER DATAGRAM PROTOCOL
Connectionless Protocol  
Provides faster, but less reliable, delivery of data.
Used in applications where low latency is more critical than guaranteed delivery, such as real-time communication (VoIP, video streaming) and Domain Name System (DNS) queries.

UDP is good for receiving calls, 
because it mostly sends data rather than validating.


[LAYER 5]- Session Layer 
The Session Layer is responsible for establishing, maintaining, and terminating sessions or connections between applications.
It manages dialogue control, allowing for full-duplex or half-duplex communication.
NetBIOS (Network Basic Input/Output System)
PPTP (Point-to-Point Tunneling Protocol)
RPC (Remote Procedure Call)



[LAYER 6]- Presentation Layer 
Responsible for translating data between the Application Layer and the lower layers.
Handles data compression, encryption, and character set conversion.
SSL/TLS (Secure Sockets Layer/Transport Layer Security)
JPEG, GIF (Image compression formats)
ASCII to EBCDIC conversion



[LAYERS  7] 
HTTP (Hypertext Transfer Protocol)
DNS (Domain Name System)
DHCP (Dynamic Host Configuration Protocol)
POP (Post Office Protocol):
IMAP (Internet Message Access Protocol)
Resolves domain names to IP addresses.
Used for web communication.





Public Address:
Route-able.
Have to pay to use it.
Has to be unique to the user.

Private Address:
1. Not routable to the internet.
2. free to use.
3. 3 segments.
4. anybody can have the same private I.P
-APIPA: (Automatic private IP Address)

Routing: 
The process of Selecting the best path in a network.

Uses a routing table or forwarding table to make decisions. 
 Routing table maintains a cord of routes to various network destinations.

Destination Address ----> next-hop I.P Address ----> forwarding table  ----> interface number(physical)

Packet forwarding:
In Summary function of routers:
-best path selections
.ruling routing algorithm.
-forwarding packets to destination
.Switch

Routing protocols:
RIP (Routing information protocol)
OSPF (open shortest path first)
BGP (Border gateway protocol)



DHCP OPERATION:

1. DHCP DISCOVER
DHCP packet is used by a device to retrieve an IP address

2. OFFER

3 DHCP REQUEST
DHCP packet a device sends once it has been offered an IP address by the DHCP server

4. DHCP ACK (Acknowledge)
DHCP packet that is sent to a device from a DHCP server


DHCP:
-Helps Tcp/ip at the network layer.
-Uses UDP for broadcast.
-Uses UDP port number 67 and 68.

DHCP Leasing process:
-Device borrows (leases) I.P Address specified time limit.


-NAT: (Network Address Translation)
-Allows a site to use a set of private addresses for internal communication and a set of global internet addresses. (at least one)


Subnets use IP addresses in three different ways:
Identify the network address
Identify the host address
Identify the default gateway




The ARP Protocol
Address Resolution Protocol

The ARP protocol allows a device to associate its MAC address with an IP address on the network. Each device on a network will keep a log of the MAC addresses associated with other devices.

When devices wish to communicate with another, they will send a broadcast to the entire network searching for the specific device. Devices can use the ARP protocol to find the MAC address (and therefore the physical identifier) of a device for communication.


How does ARP Work?
Each device within a network has a ledger to store information on, which is called a cache. In the context of the ARP protocol, this cache stores the identifiers of other devices on the network.

In order to map these two identifiers together (IP address and MAC address), the ARP protocol sends two types of messages:

ARP Request
ARP Reply
When an ARP request is sent, a message is broadcasted to every other device found on a network by the device, asking whether or not the device's MAC address matches the requested IP address. If the device does have the requested IP address, an ARP reply is returned to the initial device to acknowledge this. The initial device will now remember this and store it within its cache (an ARP entry). 


TOPOLOGIES

-BUS Topology:
1. No central device 
2. Every network node is attached to one shared bus cable.
3. When sending nodes, every device connected to the bus topology will receive the nodes. 
4. Terminators are required at both ends to prevent data reflection. Without terminators, data signals would bounce back and forth endlessly until the network collapses.  
6. Tap = Connectors
7. Dropline = Cables
cost-efficient to set up

-RING Topology:
1. All nodes are connected to a cable, forming a closed loop.
2. Data in the Token(packet) flows from one node to the next, in a circle.
3. Each node reads the data and forwards it to the next one until it reaches the destination.

-BUS && RING: are simple and inexpensive. 
1. If one single point breaks the whole system will be down.
2. Troubleshooting and maintenance are difficult.
3. Security is a major problem because every node can access all other traffic.

-STAR Topology: 
1. All nodes are individually connected to a central device, HUB or SWITCH.
2. Central point failure will crash the whole system. 
3. Easy to configure.
 expensive to set up and maintain
