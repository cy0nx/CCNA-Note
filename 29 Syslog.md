● Syslog is an industry standard protocol for message logging.

Syslog Message Format:  
![1445-07-25 17_20_17-Day 41 Slides - Syslog pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/58b6ffb3-0ac5-49a8-a8ab-efef0675613c)


Syslog Severity Levels:  
![1445-07-25 17_20_41-Day 41 Slides - Syslog pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/5226142b-5068-4685-8cae-50e2951c9283)


Syslog Message Examples:  
![1445-07-25 17_21_22-Day 41 Slides - Syslog pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/04339ae7-d20d-47fe-8b62-1b7200f26bb4)  
![1445-07-25 17_21_22-Day 41 Slides - Syslog pdf 1](https://github.com/0xVoLk/CCNA-Note/assets/100092212/e63cc3cb-5444-4e52-90f1-be3f701bd06e)


Syslog Command Summary:
```
R1(config)# logging console severity 
R1(config)# logging monitor severity 
R1(config)# logging buffered [size] severity 
R1(config)# logging server-ip 
R1(config)# logging host server-ip 
R1(config)# logging trap severity 
R1# terminal monitor
R1(config-line)# logging synchronous 
R1(config)# service timestamps log [datetime | uptime] 
R1(config)# service sequence-numbers
```
