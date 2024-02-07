● Syslog is an industry standard protocol for message logging.

Syslog Message Format:
![[1445-07-25 17_20_17-Day 41 Slides - Syslog.pdf.png]]

Syslog Severity Levels:
![[1445-07-25 17_20_41-Day 41 Slides - Syslog.pdf.png]]

Syslog Message Examples:
![[1445-07-25 17_21_22-Day 41 Slides - Syslog.pdf.png]]

![[1445-07-25 17_21_22-Day 41 Slides - Syslog.pdf 1.png]]

Syslog Command Summary:
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
