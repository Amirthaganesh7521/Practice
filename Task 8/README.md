# Working with VPNs
## Introduction
The objective of this task was to understand the role of Virtual Private Networks (VPNs) in protecting privacy and ensuring secure communication.
A VPN masks the user’s real IP address, encrypts internet traffic, and routes it through a secure server, enhancing online privacy and security.

## Tools Used
- ProtonVPN (Free Tier) – Selected for its strong reputation, no-logs policy, and availability of free servers.
- WhatIsMyIPAddress.com – Used to check public IP address before and after VPN connection.
- Speedtest.net – Used to measure and compare internet speed before and after VPN connection.
- Google Chrome Browser – Used for browsing activity verification (GitHub, YouTube).

## Steps:
 ### Install and Sign In to VPN
- For this task, we used ProtonVPN Free Tier, which is reliable and has a no-logs policy.

  <img width="1439" height="691" alt="6 1" src="https://github.com/user-attachments/assets/24573259-4f29-4e1b-a7c3-54cce1d22992" />



### Download and Install VPN Client:

- Downloaded the ProtonVPN application for Windows from the official website.
- Ran the installer and followed on-screen instructions.
- Log In to VPN Client:
- Opened the installed VPN client.
- Entered the credentials created during signup.
- Successfully logged in and accessed the VPN interface.

<img width="1000" height="645" alt="6 2" src="https://github.com/user-attachments/assets/a20238ac-45ab-49e8-a62f-1544e70e4c57" />


### Check IP and Internet Speed Before VPN

- Before connecting to the VPN, we verified the current network details:
   -   Check Public IP:
   -   Visited WhatIsMyIPAddress.com to note the public IP address.(for privacy concerns, i can't show my ip  address)


 
### Run Internet Speed Test:

-  Used Speedtest.net to measure download and upload speed.
    -  Observation:
       - Download speed: 29.79 Mbps
       - Upload speed: 34.11 Mbps.
     <img width="733" height="327" alt="6 4" src="https://github.com/user-attachments/assets/475fe585-ca91-4b83-981e-10b17de42c8f" />


### Connect to VPN and Verify
 -  Connect to VPN:
     - Opened the ProtonVPN client.
    -  Clicked the Fastest Free Option button.
     - The client connected to a server in Netherlands, assigning a new IP address.

### Check IP After VPN:

-  Visited WhatIsMyIPAddress.com again.

#### Observation:
-   IP changed to a Netherlands-based address, confirming the VPN connection.

<img width="1197" height="558" alt="6 6" src="https://github.com/user-attachments/assets/b14ce893-7e23-4a83-9859-5293a5be56ed" />

### Run Internet Speed Test After VPN:

- Used Speedtest.net to check performance while connected to VPN.

- Observation:
   -Download speed: 28.34 Mbps
   - Upload speed: 25.94 Mbps. (Slight decrease due to VPN)
 
    <img width="732" height="408" alt="6 7" src="https://github.com/user-attachments/assets/395d7a4c-ccce-4c97-af81-63d5040dc987" />

## Verify Browsing and Disconnect VPN
- Verify Secure Browsing:

- While connected to the VPN, visited the following websites to ensure traffic was routed securely:

-  GitHub – Website loaded normally.


#### Observation: 
- Both websites loaded without issues, confirming VPN was functioning and traffic was encrypted.

### Disconnect VPN:

- Disconnected from ProtonVPN using the client interface.
- Optional : revisit WhatIsMyIPAddress.com to confirm IP reverted to the original ISP address.

Step 5 – Compare IP and Internet Speed With and Without VPN
After completing the VPN session, we compared the network details before and after connecting to VPN:

### IP Address Comparison:

- Without VPN: 192.xxx.xxx.xxx (local ISP)
- With VPN (Netherlands): 212.8.249.222
 - Observation: The IP changed to a different country, confirming the VPN connection successfully masked the original IP.
- Internet Speed Comparison:

|Metric|	Without VPN|	With VPN (Netherlands)|
|------|-------------|---------------------|
|  Download Speed |	29.79 Mbps |	28.34 Mbps |
|   Upload Speed	|34.11 Mbps |	25.94 Mbps | 

Observation: Slight decrease in speed due to encryption overhead, which is normal for VPN usage.




## Conclusion
 - In this task, we gained hands-on experience using a VPN to enhance online privacy and security.
We successfully installed ProtonVPN, connected to a server in the Netherlands, verified IP address change, and observed internet speed before and after VPN connection. Browsing website like GitHub while connected confirmed that traffic was routed securely.

Through this exercise, we learned that VPNs:

- Encrypt internet traffic to prevent eavesdropping
- Hide the real IP address from websites and ISPs
- Allow access to region-restricted content
      
