● CDP is a Cisco proprietary protocol. 
● LLDP is an industry standard protocol (IEEE 802.1AB).

● CDP messages are periodically sent to multicast MAC address 0100.0CCC.CCCC.
● By default, CDP messages are sent once every 60 seconds.
● By default, the CDP holdtime is 180 seconds. If a message isn’t received from a neighbor for 180 seconds, the neighbor is removed from the CDP neighbor table.
![[1445-07-18 05_27_54-Day 36 Slides - CDP & LLDP.pdf.png]]

● R1# show cdp 
→shows basic information about CDP (timers, version) 
● R1# show cdp traffic 
→displays how many CDP messages have been sent and received 
● R1# show cdp interface 
→displays which interfaces CDP is enabled on 
● R1# show cdp neighbors 
→lists CDP neighbors and some basic information about each neighbor 
● R1# show cdp neighbors detail 
→lists each CDP neighbor with more detailed information ● 
R1# show cdp entry name 
→displays the same info as above, but for the specified neighbor only
![[1445-07-18 05_29_29-Day 36 Slides - CDP & LLDP.pdf.png]]



LLDP is an industry standard protocol (IEEE 802.1AB)
● LLDP messages are periodically sent to multicast MAC address 0180.C200.000E.
● By default, LLDP messages are sent once every 30 seconds.
● By default, the LLDP holdtime is 120 seconds.
![[1445-07-18 05_30_32-Day 36 Slides - CDP & LLDP.pdf.png]]

● R1# show lldp 
→shows basic information about LLDP (timers, version) 
● R1# show lldp traffic 
→displays how many LLDP messages have been sent and received 
● R1# show lldp interface 
→displays which interfaces LLDP tx/rx is enabled on 
● R1# show lldp neighbors 
→lists LLDP neighbors and some basic information about each neighbor 
● R1# show lldp neighbors detail 
→lists each LLDP neighbor with more detailed information 
● R1# show lldp entry name 
→displays the same info as above, but for the specified neighbor only
![[1445-07-18 05_30_18-Day 36 Slides - CDP & LLDP.pdf.png]]