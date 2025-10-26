
#  Firewall Configuration 
 ## This project demonstrates to configure and test firewall rules on Kali Linux using UFW (Uncomplicated Firewall).

### table

| Details| Commands |
|----------|----------------------------------|
| Enable Firewall    | sudo ufw enable |
| List Current Rules |sudo ufw status numbered |
| Block Telnet (Port 23)(for example)|    sudo ufw deny 23/tcp      |
| Test the Rule      |telnet localhost 23    and    nc -vz localhost 23             |
| View Status       | ufw status  |
| Remove Test Rule (Telnet Block) |  sudo ufw delete deny 23/tcp |
| Allow SSH (Port 22) (for examle) | sudo ufw allow 22/tcp |


## OUTPUT Screenshots

### Enable Firewall
Activated UFW to start filtering network traffic
<img width="1919" height="942" alt="image" src="https://github.com/user-attachments/assets/60a5ac1d-a141-4273-99cb-ab60a6afce53" />

### List Current Rules
Displayed existing rules
<img width="1919" height="942" alt="image" src="https://github.com/user-attachments/assets/9227aff8-2ce3-4f83-94c3-5c3172c9b45b" />

### Block Telnet (Port 23)
Added a deny rule
<img width="1919" height="913" alt="image" src="https://github.com/user-attachments/assets/4629400b-56eb-4c7a-a1fc-b42afa0eac69" />
Confirmed with sudo ufw status numbered.

### Allow SSH (Port 22)
Verified in ufw status
<img width="1919" height="950" alt="image" src="https://github.com/user-attachments/assets/34ca0363-3433-443f-8dab-7649c3cb817e" />

### Remove Test Rule (Telnet Block)
Deleted the Telnet deny rule to restore the firewall state:

<img width="1919" height="950" alt="image" src="https://github.com/user-attachments/assets/59c7532f-2e94-4d0a-81e0-def01484a794" />

Final rules allowed only SSH (22/tcp).


