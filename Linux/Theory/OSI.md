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
