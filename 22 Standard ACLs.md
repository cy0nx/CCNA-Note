ACLs (Access Control Lists)

ACLs function as a packet filter, instructing the router to permit or discard specific traffic.

ACLs are configured globally on the router

ACL Types:

![1445-07-10 17_15_34-Day 34 Slides - Standard ACLs pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/8684310f-a870-4732-8b4b-9646ebae308d)

Standard Numbered ACLs:

![1445-07-10 17_16_03-Day 34 Slides - Standard ACLs pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/c51b79f7-8086-45e5-8bdd-322ab34dc90b)


**R1(config)# access-list number {deny | permit} ip wildcard-mask**

![1445-07-10 17_16_57-Day 34 Slides - Standard ACLs pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/9a419a97-62c1-4c87-a0d8-b1921a153aa1)


Apply to an interface: 

**R1(config-if)# ip access-group number {in | out}**

![1445-07-10 17_17_49-Day 34 Slides - Standard ACLs pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/3826cc54-3491-4fdc-9ad2-12ef6ae4560e)
![1445-07-10 17_21_37-Day 34 Slides - Standard ACLs pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/4d07d2ad-b85f-4109-87be-3171038714f8)
![1445-07-10 17_20_20-Day 34 Slides - Standard ACLs pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/55145cf5-c91d-4bba-aa61-49b9fca8996b)


Standard Named ACLs:

Named ACLs are identified with a name (ie. ‘BLOCK_BOB’)

**R1(config)# ip access-list standard acl-name**

**R1(config-std-nacl)# [entry-number] {deny | permit} ip wildcard-mask**

![1445-07-10 17_19_41-Day 34 Slides - Standard ACLs pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/bf4dd120-348e-434b-a257-f65a245fad9e)
![1445-07-10 17_21_00-Day 34 Slides - Standard ACLs pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/05904787-bd91-4769-8251-e92b8cbfdf48)
![1445-07-10 17_22_27-Day 34 Slides - Standard ACLs pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/9fa3fe6b-ae5c-4fc7-ad2f-c8739a5ce095)
