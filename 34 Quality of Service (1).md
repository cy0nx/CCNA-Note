###  IP Phones:

● Traditional phones operate over the public switched telephone network (PSTN).  
● Sometimes this is called POTS (Plain Old Telephone Service).  
● IP phones use VoIP (Voice over IP) technologies to enable phone calls over an IP network, such as the Internet.  
● IP phones are connected to a switch just like any other end host


● IP phones have an internal 3-port switch.  
→ 1 port is the ‘uplink’ to the external switch.  
→ 1 port is the ‘downlink’ to the PC.  
→ 1 port connects internally to the phone itself. 

![1445-07-29 01_25_31-Day 46 Slides - QoS (Part 1) pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/c337e62c-8e9d-4e8b-b2fc-cd6e83520a05)  
![1445-07-29 01_25_55-Day 46 Slides - QoS (Part 1) pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/8778890f-df63-4169-abc1-950783542b8d)


###  Power over Ethernet (PoE):

● PoE allows Power Sourcing Equipment (PSE) to provide power to Powered Devices (PD) over an Ethernet cable.  
● Typically the PSE is a switch and the PDs are IP phones, IP cameras, wireless access points, etc.  
● The PSE receives AC power from the outlet, converts it to DC power, and supplies that DC power to the PDs.  
![1445-07-29 01_27_31-Day 46 Slides - QoS (Part 1) pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/5db4dd8c-a229-4157-b569-885e7b47c2da)


###  Quality of Service (QoS):

● Voice traffic and data traffic used to use entirely separate networks.  
→ Voice traffic used the PSTN  
→ Data traffic used the IP network (enterprise WAN, Internet, etc)


● QoS wasn’t necessary as the different kinds of traffic didn’t compete for bandwidth.  
![1445-07-29 01_28_41-Day 46 Slides - QoS (Part 1) pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/cb3d6400-8582-4984-85b9-97e8b6837b0e)  

● QoS is used to manage the following characteristics of network traffic:  
1) Bandwidth    
→ The overall capacity of the link, measured in bits per second (Kbps, Mbps, Gbps, etc)

2) Delay    
→ The amount of time it takes traffic to go from source to destination = one-way delay  
→ The amount of time it takes traffic to go from source to destination and return = two-way delay  
![1445-07-29 01_30_05-Day 46 Slides - QoS (Part 1) pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/d6156966-7d36-4e3e-b2de-5601fbf680fd)

3) Jitter  
→ The variation in one-way delay between packets sent by the same application

4) Loss  
→ The % of packets sent that do not reach their destination  
  
● The following standards are recommended for acceptable interactive audio (ie. phone call) quality:  
One-way delay: 150 ms or less  
Jitter: 30 ms or less  
Loss: 1% or less


● A solution to prevent tail drop and TCP global synchronization is Random Early Detection (RED).

● When the amount of traffic in the queue reaches a certain threshold, the device will start randomly dropping packets from select TCP flows.


