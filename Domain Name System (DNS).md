● DNS is used to resolve human-readable names (google.com) to IP addresses.
● Machines such as PCs don’t use names, they use addresses (ie. IPv4/IPv6).

DNS ‘A’ record = Used to map names to IPv4 addresses.
DNS ‘AAAA’ record = Used to map names to IPv6 addresses.

Standard DNS queries/responses typically use UDP. TCP is used for DNS messages greater than 512 bytes. In either case, port 53 is used.

![[1445-07-20 11_34_21-Day 38 Slides - DNS.pdf.png]]
![[1445-07-20 11_35_00-Day 38 Slides - DNS.pdf.png]]


Windows: 
		C:\Users>ipconfig /all
		C:\Users>nslookup name
		C:\Users>ipconfig /displaydns
		C:\Users>ipconfig /flushdns
		C:\Users>ping ip-address -n number

Cisco IOS:
		R1(config)#ip dns server
		R1(config)#ip host hostname ip-address
		R1(config)#ip name-server ip-address
		R1(config)#ip domain lookup
		R1(config)#ip domain name domain-name
		R1#show hosts
