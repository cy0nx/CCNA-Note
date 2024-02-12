###  DHCP Snooping  

● DHCP snooping is a security feature of switches that is used to filter DHCP messages received on untrusted ports.

● DHCP snooping only filters DHCP messages. Non-DHCP messages aren’t affected.

● All ports are untrusted by default.  
    →Usually, **uplink** ports are configured as trusted ports, and **downlink** ports remain untrusted.  
![1445-08-02 22_51_18-Day 50 Slides - DHCP Snooping pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/b4386ee1-734e-4a9d-bbd5-668bb9565100)

![1445-08-02 22_52_24-Day 50 Slides - DHCP Snooping pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/0dc107d9-5dbd-47be-8119-0ef243a3f558)

![1445-08-02 22_52_41-Day 50 Slides - DHCP Snooping pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/07df6408-f258-4fbf-9485-c43dd1e1f06d)  
<br>


### DHCP Starvation  

● An example of a DHCP-based attack is a DHCP starvation attack.  
● An attacker uses spoofed MAC addresses to flood DHCP Discover messages.  
● The target server’s DHCP pool becomes full, resulting in a denial-of-service to other devices.  
![1445-08-02 22_53_34-Day 50 Slides - DHCP Snooping pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/7d35b4e9-72fa-4849-8488-c09c8212628e)  
<br>


###  DHCP Poisoning (Man-in-the-Middle)  

● Similar to ARP Poisoning, DHCP Poisoning can be used to perform a Man-in-the-Middle attack.  
● A spurious DHCP server replies to clients’ DHCP Discover messages and assigns them IP addresses, but makes the clients use the spurious server’s IP as the default gateway.  
*Clients usually accept the first Offer message they receive.  
● This will cause the client to send traffic to the attacker instead of the legitimate default gateway.  
● The attacker can then examine/modify the traffic before forwarding it to the legitimate default gateway.  

![1445-08-02 22_54_42-Day 50 Slides - DHCP Snooping pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/80bc3b9a-508b-4aa1-a86a-6e9751ca756c)

![1445-08-02 22_55_05-Day 50 Slides - DHCP Snooping pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/395456f1-de70-49ea-b615-7bbfdabe0236)

![1445-08-02 22_55_25-Day 50 Slides - DHCP Snooping pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/e1d4f245-f377-40ec-9a7d-681baf0068c8)  
![1445-08-02 22_56_09-Day 50 Slides - DHCP Snooping pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/5c93cbf0-a741-4f25-a0d6-d48d0f7dc7cf)  
<br>


###  DHCP Messages  

● When DHCP Snooping filters messages, it differentiates between DHCP Server messages and DHCP Client messages

● Messages sent by DHCP Servers:  
    → OFFER  
    → ACK  
    → NAK = Opposite of ACK, used to decline a client’s REQUEST

● Messages sent by DHCP Clients:  
    →DISCOVER  
    →REQUEST  
    →RELEASE = Used to tell the server that the client no longer needs its IP address  
    →DECLINE = Used to decline the IP address offered by a DHCP server  
<br>


###  DHCP Snooping Operations  

● If a DHCP message is received on a trusted port, forward it as normal without inspection.

● If a DHCP message is received on an untrusted port, inspect it and act as follows:  
    → If it is a DHCP Server message, discard it.  
    → If it is a DHCP Client message, perform the following checks:

DISCOVER/REQUEST messages: Check if the frame’s source MAC address and the DHCP message’s CHADDR fields match. Match = forward, mismatch = discard

RELEASE/DECLINE messages: Check if the packet’s source IP address and the receiving interface match the entry in the DHCP Snooping Binding Table. Match = forward, mismatch = discard

● When a client successfully leases an IP address from a server, create a new entry in the
DHCP Snooping Binding Table.

![1445-08-02 22_59_18-Day 50 Slides - DHCP Snooping pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/0960b230-e521-4f31-8283-fece704c3ea1)  
<br>


###  DHCP Snooping Rate-Limiting  

● DHCP snooping can limit the rate at which DHCP messages are allowed to enter an interface.  
● If the rate of DHCP messages crosses the configured limit, the interace is err-disabled.  
● Like with Port Security, the interface can be manually re-enabled, or automatically re-enabled with errdisable recovery.  
![1445-08-02 23_00_17-Day 50 Slides - DHCP Snooping pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/06552b65-ee5a-45cd-9dea-351352204353)  
![1445-08-02 23_00_45-Day 50 Slides - DHCP Snooping pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/f8dc740c-07d1-4c1a-8ecf-f01bca6b8a00)  
<br>


###  DHCP Option 82 (Information Option)  

● Option 82, also known as the ‘DHCP relay agent information option’ is one of many DHCP options.  
● It provides additional information about which DHCP relay agent received the client’s message, on which interface, in which VLAN, etc.  
● DHCP relay agents can add Option 82 to messages they forward to the remote DHCP server.  
● With DHCP snooping enabled, by default Cisco switches will add Option 82 to DHCP messages they receive from clients, even **if the switch isn’t acting as a DHCP relay agent**.  
● By default, Cisco switches will drop DHCP messages with Option 82 that are received on an untrusted port.  
![1445-08-02 23_02_03-Day 50 Slides - DHCP Snooping pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/20f7814b-a7c3-4a84-a0d6-1a8ac1da2ea2)  
![1445-08-02 23_02_26-Day 50 Slides - DHCP Snooping pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/c87d8174-1809-4aa6-91ca-c4b929500bb1)  
![1445-08-02 23_02_45-Day 50 Slides - DHCP Snooping pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/9f0490ab-4cfa-48c5-836d-6d83c2434d04)  

```
SW1(config)# ip dhcp snooping
SW1(config)# ip dhcp snooping vlan vlan-number
SW1(config)# errdisable recovery cause dhcp-rate-limit
SW1(config)# no ip dhcp snooping information option
SW1(config-if)# ip dhcp snooping trust
SW1(config-if)# ip dhcp snooping limit rate packets-per-second
SW1# show ip dhcp snooping binding
```






