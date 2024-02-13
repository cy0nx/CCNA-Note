###  Common Terminologies  

● **Star**: When several devices all connect to one central device we can draw them in a ‘star’ shape like below, so this is often called a ‘star topology’.  
![1445-08-03 17_39_14-Day 52 Slides - LAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/9079203a-3da5-473a-95b9-eba2041eb467)

● **Full Mesh**: When each device is connected to each other device.  
![1445-08-03 17_39_44-Day 52 Slides - LAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/0795d123-6270-4575-89fa-4728b54d737b)

● **Partial Mesh**: When some devices are connected to each other, but not all.  
![1445-08-03 17_40_18-Day 52 Slides - LAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/0c0c220f-e501-4a4d-8a65-ad542798eafd)  
<br>


###  Two-Tier Campus LAN Design  

● The two-tier LAN design consists of two hierarchical layers:  
    →**Access Layer**  
    →**Distribution Layer**

● Also called a ‘Collapsed Core’ design because it omits a layer that is found in the Three Tier design: the **Core Layer**

● **Access Layer**:  
→ the layer that end hosts connect to (PCs, printers, cameras, etc.)  
→ typically Access Layer Switches have lots of ports for end hosts to connect to  
→ QoS marking is typically done here  
→ Security services like port security, DAI, etc are typically performed here  
→ switchports might be PoE-enabled for wireless APs, IP phones, etc.

● **Distribution Layer**:  
→ aggregates connections from the Access Layer Switches  
→ typically is the border between Layer 2 and Layer 3  
→ connects to services such as Internet, WAN, etc.

![1445-08-03 17_42_40-Day 52 Slides - LAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/fd8f8488-e98a-4090-b0c2-015d5b557bfa)

![1445-08-03 17_43_17-Day 52 Slides - LAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/ee8c1b61-20d3-4faa-b2ca-1c98c4fe487b)

In large LAN networks with many Distribution Layer switches (for example in separate buildings), the number of connections required between Distribution Layer switches grows rapidly  
![1445-08-03 17_44_19-Day 52 Slides - LAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/75f9e55b-27d2-4a3c-932c-584adcf3ecd0)  
To help scale large LAN networks, you can add a Core Layer. *Cisco recommends adding a Core Layer if there are more than three Distribution Layers in a single location.  
![1445-08-03 17_45_06-Day 52 Slides - LAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/2ea70ef4-fcce-49f2-afc3-6e7799bbd74a)  
<br>


###  Three-Tier Campus LAN Design  

● The three-tier LAN design consists of three hierarchical layers:  
    →**Access Layer**  
    →**Distribution Layer**  
    →**Core Layer**

● **Core Layer**:  
→ Connects Distribution Layers together in large LAN networks  
→ The focus is speed (‘fast transport’)  
→ CPU-intensive operations such as security, QoS marking/classification, etc. should be avoided at this Layer  
→ Connections are all Layer 3. No spanning-tree!  
→ Should maintain connectivity throughout the LAN even if devices fail

![1445-08-03 17_47_03-Day 52 Slides - LAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/f24c4c8a-10d9-4c23-882d-3f35bd95325c)  
<br>


###  Spine-Leaf Architecture  

● Data centers are dedicated spaces/buildings used to store computer systems such as servers and network devices.

● Traditional data center designs used a three-tier architecture (Access-Distribution-Core) like we just covered.

● This worked well when most traffic in the data center was North-South.  
![1445-08-03 17_49_48-Day 52 Slides - LAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/d7b891d1-8340-49b3-b04f-759bf8c93f82)  


● With the precedence of virtual servers, applications are often deployed in a distributed manner (across multiple physical servers), which increases the amount of East-West traffic in the data center.

● The traditional three-tier architecture led to bottlenecks in bandwidth as well as variability in the server-to-server latency depending on the path the traffic takes.

● To solve this, Spine-Leaf architecture (also called Clos architecture) has become prominent in data centers  

● There are some rules about Spine-Leaf architecture:  
    → Every Leaf switch is connected to every Spine switch.  
    → Every Spine switch is connected to every Leaf switch.  
    → Leaf switches do not connect to other Leaf switches.  
    → Spine switches do not connect to other Spine switches.  
    → End hosts (servers etc.) only connect to Leaf switches.  
● The path taken by traffic is randomly chosen to balance the traffic load among the Spine switches.  
● Each server is separated by the same number of ‘hops’ (except those connected to the same Leaf), providing consistent latency for East-West traffic.  
![1445-08-03 17_52_20-Day 52 Slides - LAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/a811d408-dc73-4342-9f22-fc30d8d1e17a)  
![1445-08-03 17_52_47-Day 52 Slides - LAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/fb9b6864-8186-4957-9a83-647b35c3599f)  
<br>


###  SOHO Networks  

● Small Office/Home Office (SOHO) refers to the office of a small company, or a small home office with few devices.  
→Doesn’t have to be an actual home ‘office’, if your home has a network connected to the Internet it is considered a SOHO network.

● SOHO networks don’t have complex needs, so all networking functions are typically provided by a single device, often called a ‘home router’ or ‘wireless router’.

● This one device can serve as a:  
→ Router  
→ Switch  
→ Firewall  
→ Wireless Access Point  
→ Modem  
![1445-08-03 17_54_23-Day 52 Slides - LAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/c738b25a-8e76-4b87-9b17-36d5c8421262)  
![1445-08-03 17_54_50-Day 52 Slides - LAN Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/3e1fb53d-e6a4-4bc2-a775-2941b670cee0)












