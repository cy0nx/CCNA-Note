In Cisco IOS, you can view the time with the show clock command
![[1445-07-19 12_45_48-Day 37 Slides - NTP.pdf.png]]
![[1445-07-19 12_46_33-Day 37 Slides - NTP.pdf.png]]

Manual Time Configuration
![[1445-07-19 12_47_11-Day 37 Slides - NTP.pdf.png]]

Hardware Clock (Calendar) Configuration
![[1445-07-19 12_47_31-Day 37 Slides - NTP.pdf.png]]

● Use the command clock ***update-calendar*** to sync the calendar to the clock’s time. 
● Use the command clock ***read-calendar*** to sync the clock to the calendar’s time.
![[1445-07-19 12_48_55-Day 37 Slides - NTP.pdf.png]]

Configuring the Time Zone
![[1445-07-19 12_52_02-Day 37 Slides - NTP.pdf.png]]

**R1# show clock 
R1# show clock detail 
R1# clock set hh:mm:ss {day|month} {month|day} year 
R1# show calendar 
R1# calendar set hh:mm:ss {day|month} {month|day} year**


● NTP (Network Time Protocol) allows automatic syncing of time over a network
● NTP uses UDP port 123 to communicate

NTP Hierarchy
![[1445-07-19 12_54_46-Day 37 Slides - NTP.pdf.png]]

'peer' is called ‘symmetric active’ mode. 
Cisco devices can operate in three NTP modes: 
● Server mode 
● Client mode 
● Symmetric active mode

![[1445-07-19 12_56_20-Day 37 Slides - NTP.pdf.png]]
![[1445-07-19 12_56_47-Day 37 Slides - NTP.pdf.png]]
![[1445-07-19 12_57_18-Day 37 Slides - NTP.pdf.png]]


Configuring NTP server mode
![[1445-07-19 12_59_43-Day 37 Slides - NTP.pdf.png]]
![[1445-07-19 12_58_58-Day 37 Slides - NTP.pdf.png]]
![[1445-07-19 12_59_50-Day 37 Slides - NTP.pdf.png]]

Configuring NTP symmetric active mode
![[1445-07-19 13_00_34-Day 37 Slides - NTP.pdf.png]]

● To configure NTP authentication: 
ntp authenticate 
ntp authentication-key key-number md5 key 
ntp trusted-key key-number 
ntp server ip-address key key-number
![[1445-07-19 13_01_33-Day 37 Slides - NTP.pdf.png]]

!Basic Configuration Commands
R1(config)# ntp server ip-address [prefer] 
R1(config)# ntp peer ip-address 
R1(config)# ntp update-calendar 
R1(config)# ntp master [stratum] 
R1(config)# ntp source interface 

!Basic Show Commands 
R1# show ntp associations 
R1# show ntp status 

!Basic Authentication Commands 
R1(config)# ntp authenticate 
R1(config)# ntp authentication-key key-number md5 key 
R1(config)# ntp trusted-key key-number 
R1(config)# ntp server ip-address key key-number 
R1(config)# ntp peer ip-address key key-number