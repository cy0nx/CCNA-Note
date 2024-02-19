##  Network Automation  

Network automation provides many key benefits:  
● Human error (typos etc.) is reduced.

● Networks become much more scalable. New deployments, network-wide changes, and troubleshooting can be implemented in a fraction of the time.

● Network-wide policy compliance can be assured (standard configurations, software versions, etc).

● The improved efficiency of network operations reduces the opex (operating expenses) of the network. Each task requires fewer man-hours.  
<br>


###  Data Plane  

● All tasks involved in forwarding user data/traffic from one interface to another are part of the **data plane**.

● A router receives a message, looks for the most specific matching route in its routing table, and forwards it out of the appropriate interface to the next hop.  
→It also de-encapsulates the original Layer 2 header, and re-encapsulates with a new header destined for the next hop’s MAC address.

● A switch receives a message, looks at the destination MAC address, and forwards it out of the appropriate interface (or floods it).  
→ This includes functions like adding or removing 802.1q VLAN tags.

● NAT (changing the src/dst addresses before forwarding) is part of the data plane.

● Deciding to forward or discard messages due to ACLs, port security, etc. is part of the data plane.

● The data plane is also called the ‘forwarding plane’.  
![1445-08-10 01_05_53-Day 59 Slides - Network Automation pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/2a0a5268-c71a-42dc-b717-bc00f5c3dcff)  
<br>


###  Control Plane  

● How does a device’s data plane make its forwarding decisions?  
→ routing table, MAC address table, ARP table, STP, etc.

● Functions that build these tables (and other functions that influence the data plane) are part of the **control plane**.

● The control plane controls what the data plane does, for example by building the router’s routing table.

● The control plane performs overhead work.  
→ OSPF itself doesn’t forward user data packets, but it informs the data plane about how packets should be forwarded.  
→ STP itself isn’t directly involved in the process of forwarding frames, but it informs the data plane about which interfaces should and shouldn’t be used to forward frames.  
→ ARP messages aren’t user data, but they are used to build an ARP table which is used in the process of forwarding data.  
![1445-08-10 01_07_19-Day 59 Slides - Network Automation pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/6481bd25-5558-4ec9-aaf2-cc138d5d38f8)  
<br>


###  Management Plane  

● Like the control plane, the **management plane** performs overhead work.  
→However, the management plane doesn’t directly affect the forwarding of messages in the data plane.

● The management plane consists of protocols that are used to manage devices.  
→SSH/Telnet, used to connect to the CLI of a device to configure/manage it.  
→Syslog, used to keep logs of events that occur on the device.  
→SNMP, used to monitor the operations of the device.  
→NTP, used to maintain accurate time on the device.  
![1445-08-10 01_08_49-Day 59 Slides - Network Automation pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/a3ab23b9-227e-4667-9048-b6b72d51ca97)  
<br>


###  Logical Planes  

● The operations of the Management plane and Control plane are usually managed by the CPU.

● However, this is not desirable for data plane operations because CPU processing is slow (relatively speaking).

● Instead, a specialized hardware ASIC (Application-Specific Integrated Circuit) is used. ASICs are chips built for specific purposes.

● Using a switch as an example:  
→When a frame is received, the ASIC (not the CPU) is responsible for the switching logic.  
→The MAC address table is stored in a kind of memory called TCAM (Ternary Content-Addressable Memory).  
*Another common name for the MAC address table is CAM table.  
→ The ASIC feeds the destination MAC address of the frame into the TCAM, which returns the matching MAC address table entry.  
→ The frame is then forwarded out of the appropriate interface.

● Modern routers also use a similar hardware data plane: an ASIC designed for forwarding logic, and tables stored in TCAM.  
<br>


###  Software-Defined Networking  

● **Software-Defined Networking (SDN)** is an approach to networking that centralizes the control plane into an application called a controller.  
→You are already familiar with this concept from learning about Wireless LAN Controllers.

● SDN is also called **Software-Defined Architecture (SDA)** or **Controller-Based Networking**.

● Traditional control planes use a distributed architecture.  
→For example, each router in the network runs OSPF and the routers share routing information and then calculate their preferred routes to each destination.

● An SDN controller centralizes control plane functions like calculating routes.  
→That is just an example, and how much of the control plane is centralized varies greatly.

● The controller can interact programmatically with the network devices using APIs (Application Programming Interface).  
![1445-08-10 01_12_49-Day 59 Slides - Network Automation pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/821ee68b-dde9-4397-baa0-c92836e0bdbc)  
<br>


###  Southbound Interface (SBI)  

● The SBI is used for communications between the controller and the network devices it controls.

● It typically consists of a communication protocol and API (Application Programming Interface).

● APIs facilitate data exchanges between programs.  
→Data is exchanged between the controller and the network devices.  
→An API on the network devices allows the controller to access information on the devices, control their data plane tables, etc.

● Some examples of SBIs:  
→OpenFlow  
→Cisco OpFlex  
→Cisco onePK (Open Network Environment Platform Kit)  
→NETCONF  
<br>


###  Northbound Interface (NBI)  

● Using the SBI, the controller communicates with the  
managed devices and gathers information about them:  
→The devices in the network  
→The topology (how the devices are connected together)  
→The available interfaces on each device  
→Their configurations

● The **Northbound Interface (NBI)** is what allows us to interact with the controller, access the data it gathers about the network, program it, and make changes in the network via the SBI.

● A REST API is used on the controller as an interface for apps to interact with it.  
→REST = Representational State Transfer

● Data is sent in a structured (serialized) format such as JSON or XML.  
→This makes it much easier for programs to use the data  
![1445-08-10 01_16_44-Day 59 Slides - Network Automation pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/c0b29bc8-70d4-41e5-8e1f-0cfe4454233e)  
<br>

**Although SDN and automation aren’t the same thing, the SDN architecture greatly facilitates the automation of various tasks in the network via the SDN controller and APIs.**
