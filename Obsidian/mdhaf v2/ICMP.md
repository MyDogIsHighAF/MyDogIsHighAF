Internet Control Message Protocol IPv4

- Gives information on stateless addresses (routers).
- From segment, to IP Datagram (layer 3), to frame (layer 2)
ICMP has 3 types of fields after IP headers
- Type
- Code
- Checksum

Access Control List (ACL) - Standard operations of procedure is to block hosts first before networks.
- Configure ACL's at router level as they are operating faster (directing information) as where server side we have firewalls.
- Firewall can be an ACL, but ACL cannot be a Firewall.

- Time Exceeded - TTL
- Redirect - First hop router sends Redirect message to source network node that a preferable route exists
- Parameter Problem - Generic error message
- Echo Request/ Echo Reply - Used for Ping
- Time Stamp & Time Stamp Reply - Routers use this message to sync their clocks for date and time
- Router Advertisement & Router Solicitation - Allow a network node not manually configured with the address of a first hop router to ask and receive information about routers on a local network
- Address Mask Request & Address Mask Reply - 

ICMP IPv6
- PMTU - Path Maximum Transmission Unit
- IPv6 fragmentation technically doesn't exist, it cuts down to PMTU but in individual packets, not fragments of a packet

Router Renumbering Messages:
Router Renumbering for IPv6 is specified in RFC 2894 and allows address prefixes on routers to be configured and reconfigured with the ease of ND and Address Autoconfiguration for network nodes. This allows administrators to update the prefixes used and advertised by IPv6 routers throughout a site.

Router Renumbering takes advantage of the vast 128-bit IPv6 address space, which provides a great deal of flexibility, allowing network administrators to assign different “meanings” to different bits in the address structure. In practice, Router Renumbering is a straightforward process. A network administrator generates at least one Router Renumbering message that provides a list of router prefixes to be renumbered. When a router receives such a message, it checks to see if any of the addresses for any of its interfaces match the prefixes in the message. If so, then the router changes the matched prefixes to the new ones learned from the message. There is an option in the Router Renumbering message that can require routers to send a Router Renumbering Result message to provide a response to the sender verifying that the renumbering message was successful.

There are three types of Router Renumbering messages:

- Commands—These are sent to routers; they have a Code value of 0.
- Results—These are responses sent by routers; they have a Code value of 1.
- Sequence Number Reset—These are used to synchronize a reset of the sequence number and cancel the cryptographic keys; they have a Code value of 255.

Each of these message types has different values in the ICMPv6 header Code fields and in the contents of the Message Body field.

The Router Renumbering message format is fairly simple, being composed of only three fields:
- IPv6 Header and Extension Headers
- ICMPv6 and Router Renumbering Header (16 octets)
- Router Renumbering Message Body
![[Pasted image 20240130110110.png]]
==***SLAAC***== stands for Stateless Address Autoconfiguration and the name pretty much explains what it does. It is a mechanism that enables each host on the network to auto-configure a unique IPv6 address without any device keeping track of which address is assigned to which node. Used to be used more instead of DHCP IPv6.

Stateless and Stateful in the context of address assignment mean the following:

A stateful address assignment involves a server or other device that keeps track of the state of each assignment. It tracks the address pool availability and resolves duplicated address conflicts. It also logs every assignment and keeps track of the expiration times.
Stateless address assignment means that no server keeps track of what addresses have been assigned and what addresses are still available for an assignment. Also in the stateless assignment scenario, nodes are responsible to resolve any duplicated address conflicts following the logic: Generate an IPv6 address, run the Duplicate Address Detection (DAD), if the address happens to be in use, generate another one and run DAD again, etc.