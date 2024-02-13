###  Dynamic ARP Inspection  

● DAI is a security feature of switches that is used to filter ARP messages received on untrusted ports.

● DAI only filters ARP messages. Non-ARP messages aren’t affected.

● All ports are untrusted by default.  
![1445-08-03 15_39_13-Day 51 Slides - Dynamic ARP Inspection pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/23cfcdfb-a916-47fc-8aad-e70edc9ef177)

![1445-08-03 15_39_42-Day 51 Slides - Dynamic ARP Inspection pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/ce8e82e5-638b-46b3-b4d4-ed7a0881c0da)

![1445-08-03 15_40_10-Day 51 Slides - Dynamic ARP Inspection pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/b968f280-11bf-4968-b328-a771c03d7014)  
<br>


###  ARP Poisoning (Man-in-the-Middle)  

● Similar to DHCP poisoning, ARP poisoning involves an attacker manipulating targets’ ARP tables so traffic is sent to the attacker.

● To do this, the attacker can send gratuitous ARP messages using another device’s IP address.

● Other devices in the network will receive the GARP and update their ARP tables, causing them to send traffic to the attacker instead of the legitimate destination.  
![1445-08-03 15_41_24-Day 51 Slides - Dynamic ARP Inspection pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/d3b7b4c0-c26a-4b02-8f0d-45cb72e99bda)

![1445-08-03 15_41_55-Day 51 Slides - Dynamic ARP Inspection pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/b3c16664-3d42-4e91-8eb0-2feae827ee4a)  
<br>


###  Dynamic ARP Inspection Operations  

● DAI inspects the sender MAC and sender IP fields of ARP messages received on untrusted ports and checks that there is a matching entry in the **DHCP snooping binding table**.  
    → If there is a matching entry, the ARP message is forwarded normally.  
    → If there isn’t a matching entry, the ARP message is discarded.  
![1445-08-03 15_43_10-Day 51 Slides - Dynamic ARP Inspection pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/f6bdb605-1d38-4bce-89b4-37365c0a92ad)  
● DAI doesn’t inspect messages received on trusted ports. They are forwarded as normal.

● ARP ACLs can be manually configured to map IP addresses/MAC addresses for DAI to check.  
    → Useful for hosts that don’t use DHCP.
    
● DAI can be configured to perform more in-depth checks also, but these are optional.

● Like DHCP snooping, DAI also supports rate-limiting to prevent attackers from overwhelming the switch with ARP messages.  
    → DHCP snooping and DAI both require work from the switch’s CPU.  
    → Even if the attacker’s messages are blocked, they can overload the switch CPU with ARP messages.  
<br>


###  DAI Configuration  

![1445-08-03 15_44_33-Day 51 Slides - Dynamic ARP Inspection pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/755f45b5-d74c-4a77-a8d3-8c896b2f66e2)  
![1445-08-03 15_45_06-Day 51 Slides - Dynamic ARP Inspection pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/5342ae71-f13c-48a3-9b64-5da2973a3fe8)  
![1445-08-03 15_45_33-Day 51 Slides - Dynamic ARP Inspection pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/51e49827-1517-464c-8e8e-9f3c4d12c72f)  
<br>


###  DAI Optional Checks  

● dst-mac: Enables validation of the destination MAC address in the Ethernet header against the target MAC address in the ARP body for ARP responses. The device classifies packets with different MAC addresses as invalid and drops them.

● ip: Enables validation of the ARP body for invalid and unexpected IP addresses. Addresses include 0.0.0.0, 255.255.255.255, and all IP multicast addresses. The device checks the sender IP addresses in all ARP requests and responses and checks the target IP addresses only in ARP responses.

● src-mac: Enables validation of the source MAC address in the Ethernet header against the sender MAC address in the ARP body for ARP requests and responses. The devices classifies packets with different MAC addresses as invalid and drops them.

![1445-08-03 15_47_49-Day 51 Slides - Dynamic ARP Inspection pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/4fc7bfdb-5b86-4643-bd64-2919ea50754c)

```
SW1(config)# ip arp inspection vlan vlan-number
SW1(config)# errdisable recovery cause arp-inspection
SW1(config)# ip arp inspection validate (src-mac | dst-mac | ip)
SW1(config-if)# ip arp inspection trust
SW1(config-if)# ip arp inspection limit rate packets [burst interval seconds]

SW1# show ip arp inspection
SW1# show ip arp inspection interfaces
```

