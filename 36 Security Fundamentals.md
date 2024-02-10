The principles of the CIA Triad form the foundation of security:

● Confidentiality  
→ Only authorized users should be able to access data.  
→ Some information/data is public and can be accessed by anyone, some is secret and should only be accessed by specific people.

● Integrity  
→ Data should not be tampered with (modified) by unauthorized users.  
→ Data should be correct and authentic.

● Availability  
→ The network/systems should be operational and accessible to authorized users.

● A vulnerability is any potential weakness that can compromise the CIA of a system/info.  
→ A potential weakness isn’t a problem on its own.

● An exploit is something that can potentially be used to exploit the vulnerability.  
→ Something that can potentially be used as an exploit isn’t a problem on it’s own.

● A threat is the potential of a vulnerability to be exploited.  
→ A hacker exploiting a vulnerability in your system is a threat.

● A mitigation technique is something that can protect against threats.  
→ Should be implemented everywhere a vulnerability can be exploited: client devices, servers, switches, routers, firewalls, etc.

###  Common Attacks

● DoS (denial-of-service) attacks  
→target the availability of a system so users can’t access it  
![1445-07-29 20_08_08-Day 48 Slides - Security Fundamentals pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/9b33487d-5ff5-4471-92f9-b9fcb01cd32c)


● Spoofing attacks  
→involve using fraudulent source IP/MAC addresses  
![1445-07-29 20_08_38-Day 48 Slides - Security Fundamentals pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/e90a0f7a-ed08-4c72-a894-96f2648d885d)


● Reflection/amplification attacks  
→involve spoofing a source IP address to cause a reflector to send lots of traffic to the target  
![1445-07-29 20_08_59-Day 48 Slides - Security Fundamentals pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/63599500-a2e7-4713-a562-ac0a25ef768b)


● Man-in-the-middle attacks  
→an attacker intercepts traffic between the source and destination to eavesdrop and/or modify the traffic  
![1445-07-29 20_09_30-Day 48 Slides - Security Fundamentals pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/8ea4e263-972d-49e0-87ef-971564a5aaa2)


● Reconnaissance attacks  
→used to gather information on the target to perform future attacks  
![1445-07-29 20_10_40-Day 48 Slides - Security Fundamentals pdf](https://github.com/0xVoLk/CCNA-Note/assets/100092212/fa8fa938-267b-436f-9f5e-2c1df455df28)


● Malware  
→malicious software such as viruses, worms, and trojan horses that infect a system  
- Viruses infect other software (a ‘host program’). The virus spreads as the software is shared by users. Typically they corrupt or modify files on the target computer.  
- Worms do not require a host program. They are standalone malware and they are able to spread on their own, without user interaction. The spread of worms can congest the network, but the ‘payload’ of a worm can cause additional harm to target devices.  
- Trojan Horses are harmful software that is disguised as legitimate software. They are spread through user interaction such as opening email attachments, or downloading a file from the Internet.

● Social engineering attacks  
→attacks that use psychological manipulation to target people and make them reveal info or perform an action  
- Phishing typically involves fraudulent emails that appear to come from a legitimate business
  → spear phishing is a more targeted form of phishing, ie. aimed at employees of a certain company.  
  → whaling is phishing targeted at high-profile individuals, ie. a company president.
- Vishing (voice phishing) is phishing performed over the phone.
- Smishing (SMS phishing) is phishing using SMS text messages.
- Watering hole attacks compromise sites that the target victim frequently visits.
- Tailgating attacks involve entering restricted, secured areas by simply walking in behind an authorized person as they enter.

● Password-related attacks  
→attacks such as dictionary attacks and brute force attacks, used to guess the target’s password  
- Guessing  
- Dictionary attack: A program runs through a ‘dictionary’ or list of common words/passwords to find the target’s password.  
- Brute force attack: A program tries every possible combination of letters, numbers, and special characters to find the target’s password.


###  Multi-factor authentication 

● involves providing more than just a username/password to prove your identity.  
● It usually involves providing two of the following (=two-factor authentication):

● Something you know  
→ a username/password combination, a PIN, etc.

● Something you have  
→ pressing a notification that appears on your phone, a badge that is scanned, etc.

● Something you are  
→ biometrics such as a face scan, palm scan, fingerprint scan, retina scan, etc.


###  AAA (triple-A) stands for Authentication, Authorization, and Accounting

● Authentication is the process of verifying a user’s identity.  
→ logging in = authentication

● Authorization is the process of granting the user the appropriate access and permissions.  
→ granting the user access to some files/services, restricting access to other files/services = authorization

● Accounting is the process of recording the user’s activities on the system.  
→ logging when a user makes a change to a file = accounting

● Enterprises typically use a AAA server to provide AAA services.  
→ ISE (Identity Services Engine) is Cisco’s AAA server.

● AAA servers usually support the following two AAA protocols:  
→ RADIUS: an open standard protocol. Uses UDP ports 1812 and 1813.  
→ TACACS+: A Cisco propriety protocol. Uses TCP port 49.
