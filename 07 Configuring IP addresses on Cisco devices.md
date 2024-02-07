
![1445-05-29 07_28_39-Lecture_ IPv4 Addressing (Part 2) _ David Bombal 1](https://github.com/0xVoLk/CCNA-Note/assets/100092212/4dbcfefd-cccb-403b-ad50-eb7c6cb1e013)

```R1>en```

```R1#show ip interface brief```

```R1#conf t```

```
R1(config)#interface gigabitethernet 0/0
R1(config-if)#ip address 10.255.255.254 255.0.0.0
R1(config-if)#no shutdown
```
```
R1(config-if)#int g0/1

R1(config-if)#ip add 172.16.255.254 255.255.0.0

R1(config-if)#no shut
```

```
R1(config-if)#int g0/2

R1(config-if)#ip add 192.168.0.254 255.255.255.0

R1(config-if)#no shut
```

```R1(config-if)#do sh ip int br```


```R1#show interface g0/0```


```
R1(config)#int g0/0

R1(config-if)#desc ## to SW1 ##

R1(config-if)#do sh int desc
```

```
R1#show running-config

R1#write
```
