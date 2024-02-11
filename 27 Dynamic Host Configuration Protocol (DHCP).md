● DHCP is used to allow hosts to automatically/dynamically learn various aspects of their network configuration, such as IP address, subnet mask, default gateway, DNS server, etc, without manual/static configuration.

DHCP messages:  
![1445-07-21 10_09_08-Day 39 Slides - DHCP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/0c60b0f7-327b-4388-bfa0-5d814da5057f)  
![1445-07-21 10_09_55-Day 39 Slides - DHCP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/6d81dac2-9b8f-40ec-ae65-99185cf1319c)


DHCP Relay  
● If the server is centralized, it won’t receive the DHCP clients’ broadcast DHCP messages. (broadcast messages don’t leave the local subnet)   
● To fix this, you can configure a router to act as a DHCP relay agent.   
● The router will forward the clients’ broadcast DHCP messages to the remote DHCP server as unicast messages.  
When the router is not a DHCP server, there are DHCP clients in the router’s connected LAN, and there is no other DHCP server in the connected LAN.  
![1445-07-21 10_10_55-Day 39 Slides - DHCP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/339fc55e-5c5b-416e-9198-afd1ab960131)  
![1445-07-21 10_13_30-Day 39 Slides - DHCP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/8e682acc-5596-4a1f-85f5-d81ed1799647)


![1445-07-21 10_11_59-Day 39 Slides - DHCP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/4cece097-a483-43e1-b58d-e4e14a51f2f5)  
![1445-07-21 10_12_45-Day 39 Slides - DHCP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/aacf929e-777e-4c47-9038-f57f5b20ee1b)



```C:\Users> ipconfig /release```

```C:\Users> ipconfig /renew```


DHCP server:
```		
R1(config)# ip dhcp excluded-address low-address high-address 
		
R1(config)# ip dhcp pool pool-name 
		
R1(dhcp-config)# network ip-address {/prefix-length | subnet-mask} 
		
R1(dhcp-config)# dns-server ip-address 
		
R1(dhcp-config)# domain-name domain-name 
		
R1(dhcp-config)# default-router ip-address 
		
R1(dhcp-config)# lease {days hours minutes | infinite} R1# show ip dhcp binding
```  

DHCP relay agent:

```R1(config-if)# ip helper-address ip-address```


DHCP client:

```R1(config-if)# ip address dhcp```
