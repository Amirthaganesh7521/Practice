# Task 3 :Perform a Basic Vulnerability Scan on Your PC
  ### Objective
  Identify security weaknesses on your own computer by running a basic vulnerability scan using Nessus Essentials or OpenVAS (Greenbone).

  
## Tools Used


|Tool|Description|Type |
|----|-----------|-----|
|Nessus Essentials |	Free vulnerability scanner by Tenable (up to 16 IPs)	|GUI / Web |
|OpenVAS (Greenbone) |	Open-source vulnerability management system|	GUI / CLI |
Operating System	| Kali Linux / Windows 10+	|Host |


 -  A vulnerability scan automatically checks a system for known weaknesses, outdated software, open ports, and insecure configurations.
 -  The scanner compares your system against a continuously updated database of CVEs (Common Vulnerabilities and Exposures).
## Steps:
### Install and Access the Scanner :

|Windows|kali(Linux)|
|-------|------------------|
|Download: https://www.tenable.com/products/nessus/nessus-essentials|sudo apt install openvas -y|
|Register → get activation key via email.| sudo apt update|
|Install and open browser → https://localhost:8834|sudo gvm-setup|
|Choose Nessus Essentials, enter key, create admin account.|sudo gvm-start and open browser → https://localhost:8834|

then we will see in browser,
<img width="885" height="797" alt="image" src="https://github.com/user-attachments/assets/39375a1d-3d2b-4c3b-9731-f6075f7bc931" />


### Target the machine: 
 -  I then proceed to create a client virtual machine. This VM is intentionally made vulnerable for these exercises. It's important to set the VM in the same region and virtual network as OpenVAS for compatibility. I install outdated versions of software like Firefox, VLC Player, and Adobe Reader to make it vulnerable.

 -  Once the vulnerable VM is ready, I configure OpenVAS to perform my first unauthenticated scan against it. I create a new target, host, and task for this process. The scan gives me insights into the VM's vulnerabilities.


<img width="1849" height="835" alt="image" src="https://github.com/user-attachments/assets/701a3e54-21a7-4aa1-b52e-3312ae69892b" />

<img width="1051" height="784" alt="image" src="https://github.com/user-attachments/assets/4a1dd57a-84af-458e-97f1-6be731028867" />

<img width="1067" height="389" alt="image" src="https://github.com/user-attachments/assets/202717b1-5f5c-4025-ab83-5d508eaf6995" />


###  Configure OpenVAS to Perform First Unauthenticated Scan Against the Vulnerable VM:



Click Assets -> Hosts -> New Hosts


<img width="956" height="191" alt="image" src="https://github.com/user-attachments/assets/05f8fd79-94c2-4cf1-9805-80aeec07498f" />


Add the Client VM's Private IP Address.


<img width="946" height="336" alt="image" src="https://github.com/user-attachments/assets/9d43ef9e-18d9-480c-8f1a-5eed968f66b3" />

Create a New Target from the Host and name it "Azure Vulnerable VMs". (like our wish)


<img width="1080" height="679" alt="image" src="https://github.com/user-attachments/assets/bf4b9384-0074-46d9-aa73-a976878aa245" />

<img width="722" height="546" alt="image" src="https://github.com/user-attachments/assets/f475f8c0-344a-4f74-9d5b-53156415d439" />

Next, Create a new Task. Under the Scans tab click Tasks and the create a new task icon.

<img width="538" height="186" alt="image" src="https://github.com/user-attachments/assets/e4985a35-613c-4e68-9549-596db4dd65b9" />

Name it "Scan - Azure Vulnerable VMs", select Azure VUlnerable VMs from the Scan Targets dropdown, and Save the Task.


<img width="949" height="148" alt="image" src="https://github.com/user-attachments/assets/a36d05b4-34a4-4864-8c4a-51660db67a68" />


<img width="956" height="135" alt="image" src="https://github.com/user-attachments/assets/c9a2d4d5-c07e-40aa-b6ce-54ce54f4f8eb" />


<img width="958" height="494" alt="image" src="https://github.com/user-attachments/assets/864f0634-77c1-4cfc-839f-98c0ea16ec80" />

 ## Execute Credentialed Scan against our Vulnerable Windows VM
  - Within OpenVAS, go to Scans -> Tasks

  - CLONE the "Windows Scan" Task, then Edit it:



<img width="960" height="623" alt="image" src="https://github.com/user-attachments/assets/e21f463c-e37e-4415-aeef-d3aeeb8a847e" />


<img width="943" height="160" alt="image" src="https://github.com/user-attachments/assets/165950a0-aff5-4d3f-9a53-79872710d674" />

<img width="938" height="841" alt="image" src="https://github.com/user-attachments/assets/edf7eb64-48aa-4136-9298-b4f187bb4aaa" />


## Verify Remediations
   - Navigate back to the Windows 10 Vulnerable VM. Instead of taking the time to update each software, I'm just going to uninstall them. I could automate this process, but since it's just a couple of programs on one VM, I will just do it manually.



<img width="1194" height="681" alt="image" src="https://github.com/user-attachments/assets/abb0e07e-54c0-49f1-9637-62e38e129f32" />

After uninstalling, restart the VM.

Navigate back to the OpenVAS webserver and re-initiate the “Scan - Azure Vulnerable VMs - Credentialed” scan and observe the results.

After the scan, I can see that compared to before vulnerabilities went down from the "Trend" column.


<img width="950" height="178" alt="image" src="https://github.com/user-attachments/assets/19254bc2-c38a-464d-a52f-f1daf0c7588d" />


I can see that many vulnerabilities left are from Microsoft Defender which may be related to disabling the Firewalls and User Account Controls on the Client VM.


