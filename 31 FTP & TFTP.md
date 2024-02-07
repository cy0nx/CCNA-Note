● FTP (File Transfer Protocol) and TFTP (Trivial File Transfer Protocol) are industry standard
protocols used to transfer files over a network.

● They both use a client-server model.

  → Clients can use FTP or TFTP to copy files from a server.
  
  → Clients can use FTP or TFTP to copy files to a server.
  
● TFTP was first standardized in 1981.

● Named ‘Trivial’ because it is simple and has only basic features compared to FTP.

  → Only allows a client to copy a file to or from a server.

  ● Every TFTP data message is acknowledged.
  
→ If the client is transferring a file to the server, the server will send Ack messages.

→ If the server is transferring a file to the client, the client will send Ack messages.

![1445-07-26 21_02_30-Day 43 Slides - FTP   TFTP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/77d76a4e-2d43-464d-906b-43b32f46945b)

![1445-07-26 21_03_02-Day 43 Slides - FTP   TFTP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/0508d2e6-0371-4976-8dc6-aee1045b4ac8)


● FTP was first standardized in 1971

● FTP uses TCP ports 20 and 21.

● Usernames and passwords are used for authentication, however there is no encryption.

![1445-07-26 21_05_27-Day 43 Slides - FTP   TFTP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/1bfa5d82-753b-41c5-9fea-19d103969a60)

![1445-07-26 21_05_55-Day 43 Slides - FTP   TFTP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/846ecb22-94e9-4719-9486-a6b9d8c8edb1)

![1445-07-26 21_07_38-Day 43 Slides - FTP   TFTP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/c816b584-4ca1-446e-9e3e-185e13b84e65)

![1445-07-26 21_08_50-Day 43 Slides - FTP   TFTP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/700a1972-a89e-44ad-bc6b-30c31c13fda1)
![1445-07-26 21_09_12-Day 43 Slides - FTP   TFTP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/6bf7bcc0-b61a-4a19-a8ce-bcd45f82a196)
![1445-07-26 21_10_26-Day 43 Slides - FTP   TFTP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/7c91acc6-372a-47c6-8c8c-b788adf11704)
![1445-07-26 21_11_32-Day 43 Slides - FTP   TFTP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/b44594e1-88e3-492b-a7c8-4be0c763be37)

![1445-07-26 21_12_27-Day 43 Slides - FTP   TFTP pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/4ddcbca5-0065-4899-a9f0-aab4ad427b85)

```
R1# show file systems
R1# show version
R1# show flash
R1# copy source destination
R1(config)# boot system filepath
R1(config)# ip ftp username username
R1(config)# ip ftp password password
```



