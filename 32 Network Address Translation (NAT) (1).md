Private IPv4 addresses are defined in RFC [1918].

Private IPv4 Addresses:

![1445-07-27 18_01_53-Day 44 Slides - NAT (Part 1) pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/65bcbecc-aa27-43f5-a8b1-46b76a4a3ea6)

● Static NAT involves statically configuring one-to-one mappings of private IP addresses to
public IP addresses.

![1445-07-27 18_03_01-Day 44 Slides - NAT (Part 1) pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/7a4e06db-5a53-4e69-9b06-4789eb5500e8)

Static NAT allows devices with private IP addresses to communicate over the Internet. However, because it requires a one-toone IP address mapping, it doesn’t help preserve IP addresses.

Static NAT Configuration:

![1445-07-27 18_21_19-Day 44 Slides - NAT (Part 1) pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/d7a91ab0-3d5d-467a-aec9-eb2576d2263c)
![1445-07-27 18_22_00-Day 44 Slides - NAT (Part 1) pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/2d556613-5aca-481c-9620-2fdd9716e365)

→ Outside Local = The IP address of the outside host, from the perspective of the local network

→ Outside Global = The IP address of the outside host, from the perspective of the outside network

![1445-07-27 18_22_45-Day 44 Slides - NAT (Part 1) pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/7b7d7e81-554f-4414-b201-22dce137262b)

![1445-07-27 18_23_14-Day 44 Slides - NAT (Part 1) pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/bd558b4b-63bb-4379-b99f-7504889e57ed)

```
R1(config-if)# ip nat inside
R1(config-if)# ip nat outside
R1(config)# ip nat inside source static inside-local-ip inside-global-ip
R1# show ip nat translations
R1# show ip nat statistics
R1# clear ip nat translation *
```
