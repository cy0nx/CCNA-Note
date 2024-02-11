In Cisco IOS, you can view the time with the show clock command  
![1445-07-19 12_45_48-Day 37 Slides - NTP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/20035913-a9c7-4875-9ee5-2c72ac07fc9a)  
![1445-07-19 12_46_33-Day 37 Slides - NTP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/e8567b46-f10c-44a5-a07d-100cda91c971)


Manual Time Configuration  
![1445-07-19 12_47_11-Day 37 Slides - NTP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/ed251414-b774-4834-a317-3dbeac94b6d3)


Hardware Clock (Calendar) Configuration  
![1445-07-19 12_47_31-Day 37 Slides - NTP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/fc6aba21-673e-45e8-a754-3f5708ffaa89)


● Use the command clock ***update-calendar*** to sync the calendar to the clock’s time.  
● Use the command clock ***read-calendar*** to sync the clock to the calendar’s time.  
![1445-07-19 12_48_55-Day 37 Slides - NTP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/66e28592-4f00-420e-a8eb-872a9996b9b3)


Configuring the Time Zone  
![1445-07-19 12_52_02-Day 37 Slides - NTP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/03c77fdc-c2a5-40cb-9afa-e82e0cfd6323)


```
R1# show clock

R1# show clock detail

R1# clock set hh:mm:ss {day|month} {month|day} year

R1# show calendar

R1# calendar set hh:mm:ss {day|month} {month|day} year
```

● NTP (Network Time Protocol) allows automatic syncing of time over a network  
● NTP uses UDP port 123 to communicate

NTP Hierarchy  
![1445-07-19 12_54_46-Day 37 Slides - NTP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/387f0924-926c-4166-9410-cf864eb22f8f)



'peer' is called ‘symmetric active’ mode.   
Cisco devices can operate in three NTP modes: 

● Server mode   
● Client mode   
● Symmetric active mode

![1445-07-19 12_56_20-Day 37 Slides - NTP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/ec9edc67-614a-43f4-b660-95c51ca54567)  
![1445-07-19 12_56_47-Day 37 Slides - NTP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/b8af3276-092a-4808-bee2-3ad8c9c01cf2)  
![1445-07-19 12_57_18-Day 37 Slides - NTP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/7fc67008-6b4f-435f-b596-bc0963e3b091)  


Configuring NTP server mode  
![1445-07-19 12_59_43-Day 37 Slides - NTP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/dfaeab5f-3273-4dff-ba2b-b4301ce2a0d4)  
![1445-07-19 12_58_58-Day 37 Slides - NTP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/b5ceb473-6132-4356-92a2-56c975a1f1f2)  
![1445-07-19 12_59_50-Day 37 Slides - NTP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/d17a31d9-65a3-4f58-9ff5-119fd0b1e2b0)


Configuring NTP symmetric active mode  
![1445-07-19 13_00_34-Day 37 Slides - NTP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/54b95a06-c54c-4d54-a50e-cc930108cf96)


● To configure NTP authentication: 
```
ntp authenticate 

ntp authentication-key key-number md5 key 

ntp trusted-key key-number 

ntp server ip-address key key-number
```
![1445-07-19 13_01_33-Day 37 Slides - NTP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/3cd91399-8c31-4bd9-b633-5a5b38780933)


!Basic Configuration Commands
```
R1(config)# ntp server ip-address [prefer] 

R1(config)# ntp peer ip-address 

R1(config)# ntp update-calendar 

R1(config)# ntp master [stratum] 

R1(config)# ntp source interface 
```

!Basic Show Commands 
```
R1# show ntp associations 

R1# show ntp status 
```

!Basic Authentication Commands 
```
R1(config)# ntp authenticate 

R1(config)# ntp authentication-key key-number md5 key 

R1(config)# ntp trusted-key key-number 

R1(config)# ntp server ip-address key key-number 

R1(config)# ntp peer ip-address key key-number
```
