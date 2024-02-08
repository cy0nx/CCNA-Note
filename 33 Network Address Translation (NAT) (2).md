● In dynamic NAT, the router dynamically maps inside local addresses to inside global addresses as
needed.

![1445-07-27 22_22_06-Day 45 Slides - NAT (Part 2) pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/57ffa9eb-08a0-4814-bc9d-e1709785a3c6)

● Although they are dynamically assigned, the mappings are still one-to-one (one inside local IP address per inside global IP address).

● If there aren’t enough inside global IP addresses available (=all are currently being used), it is called ‘NAT pool exhaustion’.

  →If a packet from another inside host arrives and needs NAT but there are no available addresses, the router will drop the packet.

  →The host will be unable to access outside networks until one of the inside global IP addresses becomes available.

  → Dynamic NAT entries will time out automatically if not used, or you can clear them manually.


  Dynamic NAT Configuration:

![1445-07-27 22_23_40-Day 45 Slides - NAT (Part 2) pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/367718dc-e967-4270-8b68-d933276352f5)
![1445-07-27 22_24_23-Day 45 Slides - NAT (Part 2) pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/da1cc411-08e7-4d3e-8a98-1d7c806d078b)
![1445-07-27 22_24_49-Day 45 Slides - NAT (Part 2) pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/89306a64-3227-4229-8283-fca52818e268)


Port Address Translation (PAT) (NAT Overload):

![1445-07-27 22_25_29-Day 45 Slides - NAT (Part 2) pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/a7f64e0d-683c-43ed-b3d5-b311bdfd0aa6)
![1445-07-27 22_27_13-Day 45 Slides - NAT (Part 2) pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/4281550c-ef4c-4059-a00b-53f762991d96)
![1445-07-27 22_27_36-Day 45 Slides - NAT (Part 2) pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/ca7c1227-537f-44e5-ae11-75283ac5540b)

PAT Configuration (interface):

![1445-07-27 22_28_15-Day 45 Slides - NAT (Part 2) pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/3d9bbc9b-2499-4c02-a340-9d73a44632e6)
![1445-07-27 22_28_57-Day 45 Slides - NAT (Part 2) pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/2b75ea90-c5a4-4b9e-89ca-df1ecd0b5c82)
![1445-07-27 22_29_29-Day 45 Slides - NAT (Part 2) pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/16d1c41f-0760-4004-8092-63a90ad4f781)

```
R1(config)# ip nat pool pool-name start-ip end-ip prefix-length prefix-length
R1(config)# ip nat pool pool-name start-ip end-ip netmask subnet-mask
R1(config)# ip nat inside source list access-list pool pool-name
R1(config)# ip nat inside source list access-list pool pool-name overload
R1(config)# ip nat inside source list access-list interface interface overload

```
