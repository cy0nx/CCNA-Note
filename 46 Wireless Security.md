###  802.11 Messages  

![1445-08-08 23_32_28-Day 56 Slides - Wireless Architectures pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/ce6ebaf4-aac5-440f-969a-f97bf6ea89b8)  
<br>


###  WLC Deployments  

● In a **split-MAC** architecture, there are four main WLC deployment models:

→ **Unified**: The WLC is a hardware appliance in a central location of the network.  
*supports about 6000 APs

→ **Cloud-based**: The WLC is a VM running on a server, usually in a private cloud in a data center. ***This is not the same as the cloud-based AP architecture dicussed previously***.  
*supports about 3000 APs

→ **Embedded**: The WLC is integrated within a switch.  
*supports about 200 APs

→ **Mobility Express**: The WLC is integrated within an AP.  
*supports about 100 APs  
<br>


###  802.1X authentication architecture  

![1445-08-09 00_02_10-Day 57 Slides - Wireless Security pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/f03f801a-5ee6-405a-96da-871d3a155c69)  
<br>


###  Encryption and Integrity Methods  

● **TKIP (Temporal Key Integrity Protocol)**  
-Based on WEP, but more secure.  
-Should not be used in modern networks.  
-WPA

● **CCMP (Counter/CBC-MAC Protocol)**  
-AES counter mode for encryption  
-CBC-MAC for MIC  
-WPA2

● **GCMP (Galois/Counter Mode Protocol)**  
-AES counter mode for encryption  
-GMAC for MIC  
-WPA3  

● A **MIC (Message Integrity Check)** is added to messages to help protect their integrity.  
<br>


###  WiFi Protected Access  

● The **WPA** certification was developed after WEP was proven to be vulnerable and includes the following protocols:  
→ TKIP (based on WEP) provides encryption/MIC.  
→ 802.1X authentication (Enterprise mode) or PSK (Personal mode)

● **WPA2** was released in 2004 and includes the following protocols:  
→ CCMP provides encryption/MIC.  
→ 802.1X authentication (Enterprise mode) or PSK (Personal mode)

● **WPA3** was released in 2018 and includes the following protocols:  
→ GCMP provides encryption/MIC.  
→ 802.1X authentication (Enterprise mode) or PSK (Personal mode)  
→ WPA3 also provides several additional security features, for example:

-**PMF (Protected Management Frames)**, protecting 802.11 management frames from eavesdropping/forging.

-**SAE (Simultaneous Authentication of Equals)** protects the four-way handshake when using personal mode authentication.

-**Forward secrecy** prevents data from being decrypted after it has been transmitted over the air. So, an attacker can’t capture wireless frames and then try to decrypt them later.
