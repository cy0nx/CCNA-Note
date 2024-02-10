● Reference bandwidth / interface bandwidth = cost (values less than 1 are converted to 1)  
● Default reference bandwidth = 100 mbps 


● Modify the reference bandwidth: ```R1(config-router)# auto-cost reference-bandwidth megabits-per-second``` 


● Manually configure the cost of an interface: ```R1(config-if)# ip ospf cost cost``` 


● Modify the interface bandwidth: ```R1(config-if)# bandwidth kilobits-per-second```  
● Total cost of outgoing interfaces = metric of the route


● Activate OSPF directly on an interface: ```R1(config-if)# ip ospf process-id area area-id```


● Configure all interfaces as passive interfaces by default: ```R1(config-router)# passive-interface default```  

![1445-07-05 16_33_43-Day 27 Slides - OSPF (Part 2) pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/b0315195-4220-4596-9131-3ea79ae4636e)
