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

