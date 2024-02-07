Extended Unique Identifier (EUI-64)

![[1445-07-09 01_33_15-Day 32 Slides - IPv6 (Part 2).pdf.png]]

![[1445-07-09 01_33_41-Day 32 Slides - IPv6 (Part 2).pdf.png]]
![[1445-07-09 01_34_01-Day 32 Slides - IPv6 (Part 2).pdf.png]]

Global unicast IPv6 addresses are public addresses
Originally defined as the 2000::/3 block (2000:: to 3FFF:FFFF:FFFF:FFFF:FFFF:FFFF:FFFF:FFFF).
![[1445-07-09 01_35_08-Day 32 Slides - IPv6 (Part 2).pdf.png]]

Unique local IPv6 addresses are private addresses
Uses the address block FC00::/7 (FC00:: to FDFF:FFFF:FFFF:FFFF:FFFF:FFFF:FFFF:FFFF)
![[1445-07-09 01_35_56-Day 32 Slides - IPv6 (Part 2).pdf.png]]

Link-local IPv6 addresses are automatically generated on IPv6-enabled interfaces.
Uses the address block FE80::/10 (FE80:: to FEBF:FFFF:FFFF:FFFF:FFFF:FFFF:FFFF:FFFF).
R1(config-if)# ipv6 enable
![[1445-07-09 01_38_47-Day 32 Slides - IPv6 (Part 2).pdf.png]]

Multicast addresses are one-to-many.
IPv6 uses range FF00::/8 for multicast. (FF00:: to FFFF:FFFF:FFFF:FFFF:FFFF:FFFF:FFFF:FFFF)
![[1445-07-09 01_37_47-Day 32 Slides - IPv6 (Part 2).pdf.png]]

Interface-local (FF01): The packet doesn’t leave the local device.
Link-local (FF02): The packet remains in the local subnet.
Site-local (FF05): The packet can be forwarded by routers.
Organization-local (FF08): Wider in scope than site-local (an entire company/organization).
Global (FF0E): No boundaries. Possible to be routed over the Internet.
![[1445-07-09 01_40_12-Day 32 Slides - IPv6 (Part 2).pdf.png]]
