
![[1445-06-10 19_58_02-Day 17 Slides - VLANs (Part 2).pdf.png]]

### Router on a Stick (ROAS)

show ip route ##Display ip route

ip route ip-address netmask next-hop ##Configure a static route, specifying the next-hop IP

ip route ip-address netmask exit-interface ##Configure a static route, specifying the exit-interface

ip route ip-address netmask exit-interface next-hop ##Configure a static route, specifying the exit-interface and next-hop IP

ip route 0.0.0.0 0.0.0.0 next-hop ##Configure a default route, specifying the next-hop IP
