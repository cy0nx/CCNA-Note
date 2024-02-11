###  Port security  

● Port security is a security feature of Cisco switches.  
● It allows you to control which source MAC address(es) are allowed to enter the switchport.  
● If an unauthorized source MAC address enters the port, an action will be taken.  
    →The default action is to place the interface in an ‘err-disabled’ state.

![1445-08-01 20_28_59-Day 49 Slides - Port Security pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/1762fd6e-dafc-4fb1-85ca-20f3aa297a76)  
![1445-08-01 20_29_11-Day 49 Slides - Port Security pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/d28dcd31-45a1-4188-bc36-83be22cf5f32)  
![1445-08-01 20_29_46-Day 49 Slides - Port Security pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/66d267f6-1166-4d18-a6f2-f93479349827)



● When you enable port security on an interface with the default settings, one MAC address is allowed.  
    →You can configure the allowed MAC address manually.  
    →If you don’t configure it manually, the switch will allow the first source MAC address that enters the interface.  
● You can change the maximum number of MAC addresses allowed.  
● A combination of manually configured MAC addresses and dynamically learned addresses is possible  
![1445-08-01 20_31_06-Day 49 Slides - Port Security pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/7c3f1886-a656-4d92-8ac2-86c7257ad082)  
<br>


Enabling Port Security:  
![1445-08-01 20_32_11-Day 49 Slides - Port Security pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/e2cf0a7f-4a6d-48e3-ba2d-b8e57855eeb5)  
![1445-08-01 20_32_41-Day 49 Slides - Port Security pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/85d6f666-a7c1-4eaf-be4b-a65002d60251)  
<br>

Re-enabling an interface (manually):
1) Disconnect the unauthorized device  
2) shutdown and then no shutdown the interface

Re-enabling an interface (ErrDisable Recovery):  
![1445-08-01 20_34_15-Day 49 Slides - Port Security pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/5946dc5c-5602-48c1-a8b2-2a68752c27b6)  
<br>


###  Violation Modes  

● Shutdown  
    → Effectively shuts down the port by placing it in an err-disabled state.  
    → Generates a Syslog and/or SNMP message when the interface is disabled.  
    → The violation counter is set to 1 when the interface is disabled.  

● Restrict  
    → The switch discards traffic from unauthorized MAC addresses.  
    → The interface is NOT disabled.  
    → Generates a Syslog and/or SNMP message each time an unauthorized MAC is detected.  
    → The violation counter is incremented by 1 for each unauthorized frame.

● Protect  
    → The switch discards traffic from unauthorized MAC addresses.  
    → The interface is NOT disabled.  
    → It does NOT generate Syslog/SNMP messages for unauthorized traffic.  
    → It does NOT increment the violation counter.  
    <br>


Violation mode: Restrict  
![1445-08-01 20_36_43-Day 49 Slides - Port Security pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/af812a63-2689-465b-8e84-5448b0474fc6)


Violation mode: Protect  
![1445-08-01 20_37_12-Day 49 Slides - Port Security pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/732e5631-a0ed-42f7-8bfb-f2af054193ff)  
<br>


###  Secure MAC address aging  

● By default secure MAC addresses will not ‘age out’ (Aging Time : 0 mins)  
→ Can be configured with switchport port-security aging time minutes

● The default aging type is Absolute  
    → Absolute: After the secure MAC address is learned, the aging timer starts and the MAC is removed after the timer expires, even if the switch continues receiving frames from that source MAC address.  
    → Inactivity: After the secure MAC address is learned, the aging timer starts but is reset every time a frame from that source MAC address is received on the interface.  
    → Aging type is configured with switchport port-security aging type {absolute | inactivity}
    
● Secure Static MAC aging (addresses configured with switchport port-security mac-address x.x.x) is disabled by default.  
    → Can be enabled with switchport port-security aging static  
![1445-08-01 20_39_16-Day 49 Slides - Port Security pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/e23ca218-03f2-416e-afc1-6cdb6b3bac87)  
<br>


###  Sticky Secure MAC Addresses  

● When enabled, dynamically-learned secure MAC addresses will be added to the running config.

● The ‘sticky’ secure MAC addresses will never age out.  
→ You need to save the running-config to the startup-config to make them truly permanent (or else they will not be kept if the switch restarts)

● When you issue the ```switchport port-security mac-address sticky``` command, all current dynamically-learned secure MAC addresses will be converted to sticky secure MAC addresses.  
![1445-08-01 20_41_44-Day 49 Slides - Port Security pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/99c4b4b1-575e-4169-b41a-f7105f9e428c)  
<br>


###  MAC Address Table  

● Secure MAC addresses will be added to the MAC address table like any other MAC address.  
    → Sticky and Static secure MAC addresses will have a type of STATIC  
    → Dynamically-learned secure MAC addresses will have a type of DYNAMIC  
    → You can view all secure MAC addresess with show mac address-table secure  
![1445-08-01 20_43_01-Day 49 Slides - Port Security pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/f135904e-30d4-41b9-ae0e-53b2521fc99c)

```
SW1# show mac address-table secure
SW1# show port-security
SW1# show port-security interface interface
SW1# show errdisable recovery
SW1(config)# errdisable recovery cause psecure-violation
SW1(config)# errdisable recovery interval seconds
SW1(config-if)# switchport port-security
SW1(config-if)# switchport port-security mac-address mac-address
SW1(config-if)# switchport port-security mac-address sticky
SW1(config-if)# switchport port-security violation {shutdown | restrict | protect}
SW1(config-if)# switchport port-security aging time minutes
SW1(config-if)# switchport port-security aging type {absolute | inactivity}
SW1(config-if)# switchport port-security aging static
```




