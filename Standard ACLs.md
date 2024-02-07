ACLs (Access Control Lists)
ACLs function as a packet filter, instructing the router to permit or discard specific traffic.
ACLs are configured globally on the router

ACL Types:
![[1445-07-10 17_15_34-Day 34 Slides - Standard ACLs.pdf.png]]

Standard Numbered ACLs:
![[1445-07-10 17_16_03-Day 34 Slides - Standard ACLs.pdf.png]]
**R1(config)# access-list number {deny | permit} ip wildcard-mask**
![[1445-07-10 17_16_57-Day 34 Slides - Standard ACLs.pdf.png]]
Apply to an interface: 
**R1(config-if)# ip access-group number {in | out}**
![[1445-07-10 17_17_49-Day 34 Slides - Standard ACLs.pdf.png]]
![[1445-07-10 17_21_37-Day 34 Slides - Standard ACLs.pdf.png]]
![[1445-07-10 17_20_20-Day 34 Slides - Standard ACLs.pdf.png]]


Standard Named ACLs:
Named ACLs are identified with a name (ie. ‘BLOCK_BOB’)
**R1(config)# ip access-list standard acl-name**
**R1(config-std-nacl)# [entry-number] {deny | permit} ip wildcard-mask**
![[1445-07-10 17_19_41-Day 34 Slides - Standard ACLs.pdf.png]]
![[1445-07-10 17_21_00-Day 34 Slides - Standard ACLs.pdf.png]]
![[1445-07-10 17_22_27-Day 34 Slides - Standard ACLs.pdf.png]]

