Numbered ACLs use the following ranges: 100 – 199, 2000 – 2699
***R1(config)# access-list number [permit | deny] protocol src-ip dest-ip*** 

***R1(config)# ip access-list extended {name | number} 
R1(config-ext-nacl)# [seq-num] [permit | deny] protocol src-ip dest-ip***
![[1445-07-14 04_24_08-Day 35 Slides - Extended ACLs.pdf.png]]

**R1(config-ext-nacl)#deny tcp src-ip eq src-port-num dest-ip eq dst-port-num****
![[1445-07-14 04_28_31-Day 35 Slides - Extended ACLs.pdf.png]]

![[1445-07-14 04_29_06-Day 35 Slides - Extended ACLs.pdf.png]]
![[1445-07-14 04_29_40-Day 35 Slides - Extended ACLs.pdf.png]]


![[1445-07-14 04_31_10-(23) Free CCNA _ Extended ACLs _ Day 35 _ CCNA 200-301 Complete Course - YouTube.png]]
![[1445-07-14 04_31_35-(23) Free CCNA _ Extended ACLs _ Day 35 _ CCNA 200-301 Complete Course - YouTube.png]]

