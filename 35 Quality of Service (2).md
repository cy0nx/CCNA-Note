● The purpose of QoS is to give certain kinds of network traffic priority over others during congestion.

→ NBAR (Network Based Application Recognition) performs a deep packet inspection, looking beyond the Layer 3 and Layer 4 information up to Layer 7 to identify the specific kind of traffic.

Layer 2 header field can be used for QoS markings:  
The PCP (Priority Code Point) field of the 802.1Q tag (in the Ethernet header) can be used to identify high/low priority traffic.  
→Only when there is a dot1q tag!  
![1445-07-29 18_45_13-Day 47 Slides - QoS (Part 2) pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/dbc4cc67-133b-4359-a4f6-7d8a461001ce)


Layer 3 header field can be used for QoS markings:  
DSCP (formerly IPP)

→ Default Forwarding (DF) – best effort traffic (The DSCP marking for DF is 0.)  
→ Expedited Forwarding (EF) – low loss/latency/jitter traffic (usually voice) (The DSCP marking for EF is 46.)  
→ Assured Forwarding (AF) – A set of 12 standard values  
→ Class Selector (CS) – A set of 8 standard values, provides backward compatibility with IPP  

AF:  
![1445-07-29 18_50_38-Day 47 Slides - QoS (Part 2) pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/f0881ec3-1507-42f1-972c-07ec2a71bd6c)

CS:  
![1445-07-29 18_51_56-Day 47 Slides - QoS (Part 2) pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/2d54e28c-88e4-4bd1-9cd5-1144a89660c2)

● The RFC 4594 offers many specific recommendations, but here are a few key ones:  
→ Voice traffic: EF  
→ Interactive video: AF4x  
→ Streaming video: AF3x  
→ High priority data: AF2x  
→ Best effort: DF  

● The trust boundary of a network defines where devices trust/don’t trust the QoS markings of received messages.  
● If the markings are trusted, the device will forward the message without changing the markings.  
● If the markings aren’t trusted, the device will change the markings according to the configured policy.

● CBWFQ (Class-Based Weighted Fair Queuing) is a popular method of scheduling, using a weighted roundrobin scheduler while guaranteeing each queue a certain percentage of the interface’s bandwidth during congestion.

● LLQ (Low Latency Queuing) designates one (or more) queues as strict priority queues.  
→ This means that if there is traffic in the queue, the scheduler will always take the next packet from that queue until it is empty.

● Shaping buffers traffic in a queue if the traffic rate goes over the configured rate.  
● Policing drops traffic if the traffic rate goes over the configured rate.


