###  WAN Architectures  

● WAN stands for Wide Area Network.

● Although the Internet itself can be considered a WAN, the term WAN is typically used to refer to an enterprise’s private connections that connect their offices, data centers, and other sites together.

● Over public/shared networks like the Internet, VPNs (Virtual Private Networks) can be used to create private WAN connections.  
<br>



###  WAN over dedicated connection (Leased Line)  

![1445-08-03 23_28_46-Day 53 Slides - WAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/735bb188-98ea-4347-8181-b201807192dc)  
![1445-08-03 23_29_22-Day 53 Slides - WAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/e4204ff6-5908-4643-8aba-5dd0a96fe286)  
<br>


###  WAN connection via Ethernet (Fiber)  

![1445-08-03 23_30_45-Day 53 Slides - WAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/0304d680-7f35-446b-91f1-e33233da4df7)  
<br>


###  WAN over shared infrastructure (Internet VPN)  

![1445-08-03 23_31_37-Day 53 Slides - WAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/1428e926-9605-459f-b769-b694b583e84d)  
<br>


###  Leased Lines  

● A **leased line** is a dedicated physical link, typically connecting two sites.

● Leased lines use serial connections (PPP or HDLC encapsulation).

● There are various standards that provide different speeds, and different standards are available in different countries.  
![1445-08-03 23_33_10-Day 53 Slides - WAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/aeb2348b-ffd8-4ec3-b9b0-c52590db67f2)  
● Due to the higher cost, higher installation lead time, and slower speeds of leased lines, Ethernet WAN technologies are becoming more popular.  
<br>


### MPLS  

● MPLS stands for ‘Multi Protocol Label Switching’.

● Similar to the Internet, service providers’ MPLS networks are shared infrastructure because many customer enterprises connect to and share the same infrastructure to make WAN connections.

● However, the label switching in the name of MPLS allows VPNs to be created over the MPLS infrastructure through the use of **labels**.

● Some important terms:  
CE router = Customer Edge router  
PE router = Provider Edge router  
P router = Provider core router

● When the PE routers receive frames from the CE routers, they add a label to the frame.

● These labels are used to make forwarding decisions within the service provider network, ***not the destination IP***.  
![1445-08-03 23_35_18-Day 53 Slides - WAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/d9165d17-b6b7-4d95-901a-ebcc678e7729)  

● The CE routers do not use MPLS, it is only used by the PE/P routers.

● When using a Layer 3 MPLS VPN, the CE and PE routers peer using OSPF, for example, to share routing information.

● For example, in the diagram below Office A’s CE will peer with one PE, and Office B’s CE will peer with the other PE.

● Office A’s CE will learn about Office B’s routes via this OSPF peering, and Office B’s CE will learn about Office A’s routes too.  
![1445-08-03 23_36_48-Day 53 Slides - WAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/40e32f95-372f-4dbd-be8b-83ec1ce60519)

● When using a Layer 2 MPLS VPN, the CE and PE routers do not form peerings.

● The service provider network is entirely transparent to the CE routers.

● In effect, it is like the two CE routers are directly connected.  
→ Their WAN interfaces will be in the same subnet.

● If a routing protocol is used, the two CE routers will peer directly with each other.

● Many different technologies can be used to connect to a service provider’s MPLS network for WAN service.  
![1445-08-03 23_37_48-Day 53 Slides - WAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/c7d014cb-2d4c-419b-a863-3d00b70d1f90)  
<br>


###  Internet Connections  

● For example, private WAN technologies such as leased lines and MPLS VPNs can be used to connect to a service provider’s Internet infrastructure.

● In addition, technologies such as CATV and DSL commonly used by consumers (home Internet access) can also be used by an Enterprise.

● These days, for both enterprise and consumer Internet access, fiber optic Ethernet connections are growing in popularity due to the high speeds they provide over long distances.  
<br>


###  Digital Subscriber Line (DSL)  

● DSL provides Internet connectivity to customers over phone lines, and can share the same phone line that is already installed in most homes.

● A DSL modem (modulator-demodulator) is required to convert data into a format suitable to be sent over the phone lines.  
→ The modem might be a separate device, or it might be incorporated in to the ‘home router’.  
![1445-08-03 23_40_00-Day 53 Slides - WAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/a570212c-63e4-4600-90a1-7ea2616e3f27)  
<br>


###  Cable Internet  

● Cable Internet provides Internet access via the same CATV (Cable Television) lines used for TV service.

● Like DSL, a cable modem is required to convert data into a format suitable to be sent over the CATV cables.  
→ Like a DSL modem, this can be a separate device or built into the home router.  
![1445-08-03 23_41_04-Day 53 Slides - WAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/e633927f-6d61-48e4-8879-5bbab6bbe336)  
<br>


###  Redundant Internet Connections  

![1445-08-03 23_41_48-Day 53 Slides - WAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/1d80147e-1651-48b1-b87a-c900e2abb628)  
<br>


###  Internet VPNs  

● We will cover two kinds of Internet VPNs:  
1) Site-to-Site VPNs using IPsec  
2) Remote-access VPNs using TLS
<br>


###  Site-to-Site VPNs (IPsec)  

● A ‘site-to-site’ VPN is a VPN between two devices and is used to connect two sites together over the Internet.

● A VPN ‘tunnel’ is created between the two devices by encapsulating the original IP packet with a VPN header and a new IP header.  
→ When using IPsec, the original packet is encrypted before being encapsulated with the new header  
![1445-08-03 23_43_39-Day 53 Slides - WAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/1913b118-6b0c-4823-aee5-5c67ee896ef1)

● Let’s summarize that process:  
1) The sending device combines the original packet and session key (encryption key) and runs them through an encryption formula.  
2) The sending device encapsulates the encrypted packet with a VPN header and a new IP header.  
3) The sending device sends the new packet to the device on the other side of the tunnel.  
4) The receiving device decrypts the data to get the original packet, and then forwards the original packet to its destination.

● In a ‘site-to-site’ VPN, a tunnel is formed only between two tunnel endpoints (for example, the two routers connected to the Internet).

● All other devices in each site don’t need to create a VPN for themselves. They can send unencrypted data to their site’s router, which will encrypt it and forward it in the tunnel as described above.

● There are some limitations to standard IPsec:

1) IPsec doesn’t support broadcast and multicast traffic, only unicast. This means that routing protocols such as OSPF can’t be used over the tunnels, because they rely on multicast traffic.  
→ This can be solved with ‘GRE over IPsec’

2) Configuring a full mesh of tunnels between many sites is a labor-intensive task.  
→ This can be solved with Cisco’s DMVPN.

● Let’s look at each of the above solutions.  
<br>


###  GRE over IPsec  

● GRE (Generic Routing Encapsulation) creates tunnels like IPsec, however it does not encrypt the original packet, so it is not secure.

● However, it has the advantage of being able to encapsulate a wide variety of Layer 3 protocols as well as broadcast and multicast messages.

● To get the flexibility of GRE with the security of IPsec, ‘GRE over IPsec’ can be used.

● The original packet will be encapsulated by a GRE header and a new IP header, and then the GRE packet will be encrypted and encapsulated within an IPsec VPN header and new IP header.  
![1445-08-03 23_46_10-Day 53 Slides - WAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/35b827f9-83d3-42ba-be21-d9906778c521)  
<br>


###  DMVPN  

● DMVPN (Dynamic Multipoint VPN) is a Cisco-developed solution that allows routers to dynamically create a full mesh of IPsec tunnels without having to manually configure every single tunnel.  
![1445-08-03 23_46_54-Day 53 Slides - WAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/b3ad614e-7b5b-4551-b621-58a99272880b)  
<br>


###  Remote-Access VPNs  

● Whereas site-to-site VPNs are used to make a point-to-point connection between two sites over the Internet, remote-access VPNs are used to allow end devices (PCs, mobile phones) to access the company’s internal resources securely over the Internet.

● Remote-access VPNs typically use TLS (Transport Layer Security).  
→ TLS is also what provides security for HTTPS (HTTP Secure)  
→ TLS was formerly known as SSL (Secure Sockets Layer) and developed by Netscape, but it was renamed to TLS when it was standardized by the IETF.

● VPN client software (for example Cisco AnyConnect) is installed on end devices (for example companyprovided laptops that employees use to work from home).

● These end devices then form secure tunnels to one of the company’s routers/firewalls acting as a TLS server.

● This allows the end users to securely access resources on the company’s internal network without being directly connected to the company network.  
![1445-08-03 23_48_32-Day 53 Slides - WAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/93e4d178-dd88-4497-8725-2d214c40fc62)  
<br>


###  Site-to-Site vs Remote-Access VPN  

● **Site-to-Site** VPNs typically use IPsec.  
● **Remote-Access** VPNs typically use TLS.

● **Site-to-Site** VPNs provide service to many devices within the sites they are connecting.  
● **Remote-Access** VPNs provide service to the one end device the VPN client software is installed on.

● **Site-to-Site** VPNs are typically used to permanently connect two sites over the Internet.  
● **Remote-Access** VPNs are typically used to provide on-demand access for end devices that want to securely access company resources while connected to a network which is not secure.








