Solicited-Node Multicast Address
![[1445-07-10 00_45_14-Day 33 Slides - IPv6 (Part 3).pdf.png]]

Neighbor Discovery Protocol (NDP) is a protocol used with IPv6 replace ARP
Two message types are used: 
1) Neighbor Solicitation (NS) = ICMPv6 Type 135 
2) Neighbor Advertisement (NA) = ICMPv6 Type 136

Neighbor Solicitation (NS)
![[1445-07-10 00_46_58-Day 33 Slides - IPv6 (Part 3).pdf.png]]

Neighbor Advertisement (NA)
![[1445-07-10 00_47_07-Day 33 Slides - IPv6 (Part 3).pdf.png]]

Another function of NDP allows hosts to automatically discover routers on the local network.
1) Router Solicitation (RS) = ICMPv6 Type 133
	→ Sent to multicast address FF02::2 (all routers). 
	→ Asks all routers on the local link to identify themselves. 
	→ Sent when an interface is enabled/host is connected to the network
	
1) Router Advertisement (RA) = ICMPv6 Type 134
	→ Sent to multicast address FF02::1 (all nodes). 
	→ The router announces its presence, as well as other information about the link. 
	→ These messages are sent in response to RS messages. 
	→ They are also sent periodically, even if the router hasn’t received an RS.

Stateless Address Auto-configuration (SLAAC)
Using the **ipv6 address autoconfig** command, you don’t need to enter the prefix. 
The device uses NDP to learn the prefix used on the local link. 
● The device will use EUI-64 to generate the interface ID, or it will be randomly generated (depending on the device/maker)
![[1445-07-10 00_52_58-Day 33 Slides - IPv6 (Part 3).pdf.png]]

Duplicate Address Detection (DAD) allows hosts to check if other devices on the local link are using the same IPv6 address.

IPv6 routing is disabled by default, and must be enabled with **ipv6 unicast-routing**


IPv6 Static Routing

Recursive static route: Only the next hop is specified.
***ipv6 route destination/prefix-length next-hop***
**R1(config)# ipv6 route 2001:db8:0:3::/64 2001:db8:0:12::2**

Fully specified static route: Both the exit interface and next hop are specified.
***ipv6 route destination/prefix-length exit-interface next-hop***
R1(config)# ipv6 route 2001:db8:0:3::/64 g0/0 2001:db8:0:12::2
![[1445-07-10 00_56_46-Day 33 Slides - IPv6 (Part 3).pdf.png]]
![[1445-07-10 00_56_58-Day 33 Slides - IPv6 (Part 3).pdf.png]]

