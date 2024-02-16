###  Wireless Networks  

● Although we will briefly look at other types of wireless networks, in this section of the course we will be focusing on wireless LANs using Wi-Fi.

● The standards we use for wireless LANs are defined in IEEE 802.11.

● The term **Wi-Fi** is a trademark of the **Wi-Fi Alliance**, not directly connected to the IEEE.

● The Wi-Fi Alliance tests and certifies equipment for 802.11 standards compliance interoperability with other devices.

● However, Wi-Fi has become the common term that people use to refer to 802.11 wireless LANs, and I will use both terms throughout these videos.

● Wireless networks have some issues that we need to deal with.  
1) All devices within range receive all frames, like devices connected to an Ethernet hub.
![1445-08-07 00_30_42-Day 55 Slides - Wireless Fundamentals pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/bea09bcf-4fc4-4cc6-91ef-899a43eaf853)  
→Privacy of data within the LAN is a greater concern.  
→CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance) is used to facilitate half-duplex communications.

● **CSMA/CD** is used in wired networks to detect and recover from collisions.  
● **CSMA/CA** is used in wireless networks to avoid collisions.

● When using **CSMA/CA**, a device will wait for other devices to stop transmitting before it transmits data itself.  
![1445-08-07 00_32_00-Day 55 Slides - Wireless Fundamentals pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/3182a433-a0c7-4a3a-baf9-f07d74a8dde7)

2) Wireless communications are regulated by various international and national bodies.

3) Wireless signal coverage area must be considered.  
→ Signal range.  
→ Signal **absorption, reflection, refraction, diffraction, and scattering**.

● **Absorption** happens when a wireless signal passes through a material and is converted into heat, weakening the original signal.  
![1445-08-07 00_34_00-Day 55 Slides - Wireless Fundamentals pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/66395581-3f96-4fbc-96b7-d9ee6ebdc8e0)

● **Reflection** happens when a signal bounces off of a material, for example metal.  
→ This is why Wi-Fi reception is usually poor in elevators. The signal bounces off the metal and very little penetrates into the elevator.  
![1445-08-07 00_34_44-Day 55 Slides - Wireless Fundamentals pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/458cab50-d117-4514-9634-41764fccb022)

● **Refraction** happens when a wave is bent when entering a medium where the signal travels at a different speed.  
→ For example, glass and water can refract waves.  
![1445-08-07 00_35_45-Day 55 Slides - Wireless Fundamentals pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/4a4bcb6a-d02d-4cdc-847f-d9c5831660fe)

● **Diffraction** happens when a wave encounters an obstacle and travels around it.  
→This can result in ‘blind spots’ behind the obstacle.  
![1445-08-07 00_36_22-Day 55 Slides - Wireless Fundamentals pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/2674e45f-551a-42c7-a194-272cf7e5c2cc)

● **Scattering** happens when a material causes a signal to scatter in all directions.  
→Dust, smog, uneven surfaces, etc. can cause scattering.  
![1445-08-07 00_37_07-Day 55 Slides - Wireless Fundamentals pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/34f38388-648b-4344-bb26-08818bc5b053)

4) Other devices using the same channels can cause interference.  
→ For example, a wireless LAN in your neighbor’s house/apartment.
<br>


### Radio Frequency  

● To send wireless signals, the sender applies an alternating current to an antenna.  
→This creates electromagnetic fields which propagate out as waves.

● Electromagnetic waves can be measured in multiple ways for example **amplitude** and **frequency**.

● **Amplitude** is the maximum strength of the electric and magnetic fields.  
![1445-08-07 00_38_53-Day 55 Slides - Wireless Fundamentals pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/b76fc250-a7b0-4740-ad2e-1cefff2ff2a7)

● **Frequency** measures the number of up/down cycles per a given unit of time.

● The most common measurement of frequency is **hertz**.  
→ Hz (Hertz) = cycles per second  
→ kHz (Kilohertz) = 1,000 cycles per second  
→ MHz (Megahertz) = 1,000,000 cycles per second  
→ GHz (Gigahertz) = 1,000,000,000 cycles per second  
→ THz (Terahertz) = 1,000,000,000,000 cycles per second  
![1445-08-07 00_40_06-Day 55 Slides - Wireless Fundamentals pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/a44adc22-9339-46e3-8e62-dd35c800a8e4)  

![1445-08-07 00_40_36-Day 55 Slides - Wireless Fundamentals pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/0b5041fb-2e8b-48de-beb3-7ed7395df63c)  
● Another important term is **period**, the amount of time of one cycle.  
→ If the **frequency** is 4 Hz, the **period** is 0.25 seconds.  
<br>


###  Radio Frequency Bands  

● Wi-Fi uses two main bands (frequency ranges)

● **2.4 GHz** band  
→ The actual range is **2.400 GHz** to **2.4835 GHz**

● **5 GHz** band  
→ The actual range is from **5.150 GHz** to **5.825 GHz**
 
● The 2.4 GHz band typically provides further reach in open space and better penetration of obstacles such as walls.
→ However, more devices tend to use the 2.4 GHz band so interference can be a bigger
problem compared to the 5 GHz band.
● ***Wi-Fi 6** (802.11ax)has expanded the spectrum range to include a band in the **6 GHz** range.  
<br>


###  Channels  

● Each band is divided up into multiple ‘channels’.  
→ Devices are configured to transmit and receive traffic on one (or more) of these channels.

● The 2.4 GHz band is divided into several channels, each with a 22 MHz range.

● In a small wireless LAN with only a single AP, you can use any channel.

● However, in larger WLANs with multiple APs, it’s important that adjacent APs don’t use overlapping channels. This helps avoid interference.

● In the 2.4 GHz band, it is recommended to use channels 1, 6, and 11.  
![1445-08-07 00_44_41-Day 55 Slides - Wireless Fundamentals pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/2842fc7c-0460-40d5-ad94-1a4e5e7b3e4b)  
● The 5 GHz band consists of non-overlapping channels, so it is much easier to avoid interference between adjacent APs  
<br>


###  802.11 Standards  

![1445-08-07 00_45_40-Day 55 Slides - Wireless Fundamentals pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/731bf254-90ac-4037-9d8e-d21a8bc383f6)  
<br>


###  Service Sets

