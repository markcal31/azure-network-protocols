<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
Project Summary: This Project is a walkthrough of the steps I took to showcase various network protocols in action using Microsoft Azure in the Windows 10 operating System. Using Wireshark to monitor different protocol traffic, we can observe various network traffic to and from Azure Virtual Machines. In this project, we also experiment with Network Security Groups which serve as firewalls between virtual machines.


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Part 1 (Create Resources)
- Part 2 (Observe ICMP Traffic)
- Part 3 (Observe SSH Traffic)
- Part 4 (Observe DHCP Traffic)
- Part 5 (Observe DNS Traffic)
- Part 6 (Observe RDP Traffic)

<h2>Actions and Observations</h2>

<p>
<br>Part 1 (Create Resources) </b>
  <br> - Created a Resource Group </b>
  <br> - While creating VM1, i selected the previously created Resource Group (RG-LAB-02)  </b>
  <br> - While creating VM1, i allowed it to create a new Virtual Network (Vnet) and Subnet in the Networking tab </b>
  <br> - Created a Linux (Ubuntu) VM (VM2) </b>
  <br> - While creating VM2, I selected the previously created Resource Group and Vnet (VM1-vnet) so that both VM's were on the same subnet </b>
  <br> - Observed the Virtual Network within Network Watcher </b>
</p>

![image](https://github.com/user-attachments/assets/e007815c-88b7-4193-a16c-6e7558048362)

![image](https://github.com/user-attachments/assets/1e2dd2f7-adee-4412-9612-43d158ec113a)

![image](https://github.com/user-attachments/assets/d3be7b2a-76d3-4692-868c-366f086df230)

![image](https://github.com/user-attachments/assets/1795913d-dca0-4b9d-97da-90bd28cc69a4)

![image](https://github.com/user-attachments/assets/e9f5960b-5801-49d3-bf93-01732c1fc63d)

<p>
<br> Part 2 (Observe ICMP Traffic) </b>
  <br> - Used Remote Desktop to connect to the Windows 10 Virtual Machine </b>
  <br> - Installed Wireshark in VM1 </b>
  <br> - Opened Wireshark and filtered for ICMP traffic only </b>
  <br> - Retrieved the private IP address of the Ubuntu VM (VM2) and attempted to ping it from within the Windows 10 VM
 </b>
  <br> - Observed ping requests and replies within WireShark </b>
  <br> - From The Windows 10 VM, opene PowerShell and attempted to ping a public website (such as www.google.com) and observed the traffic in WireShark </b>
  <br> - Initiated a perpetual/non-stop ping from the Windows 10 VM (VM1) to THE Ubuntu VM (VM2)
 </b>
 <br> - Opened the Network Security Group the Ubuntu VM (VM2) is using and disabled incoming (inbound) ICMP traffic
 </b>
  <br> - Back in the Windows 10 VM (VM1), observed the ICMP traffic in WireShark and the command line Ping activity
 </b>
 <br> - Re-enabled ICMP traffic for the Network Security Group the Ubuntu VM (VM2) is using
 </b>
  <br> - Back in the Windows 10 VM (VM1), observed the ICMP traffic in WireShark and the command line Ping activity start working again.
 </b>
</p>

![image](https://github.com/user-attachments/assets/b6b31246-e091-4be4-8b51-6832bd5df1f4)

![image](https://github.com/user-attachments/assets/7a23f59a-4a9d-430f-955c-f97ac24f5779)

![image](https://github.com/user-attachments/assets/e45250e8-7904-4bcf-9bf0-2be3c66810fe)

![image](https://github.com/user-attachments/assets/fe3a1835-2db5-41c4-8023-733e44b81aeb)

![image](https://github.com/user-attachments/assets/2bbfc85e-1485-4a3a-882b-06167cb32e32)

![image](https://github.com/user-attachments/assets/fbdef5a1-92d2-4441-8898-52b65b0febfc)

![image](https://github.com/user-attachments/assets/555ea711-e927-4818-9e27-84870ac3795d)

![image](https://github.com/user-attachments/assets/eae0fa05-a0a2-42e5-aa4e-787152940e91)

![image](https://github.com/user-attachments/assets/a3ea863b-f95e-4a53-8c9d-1134d60b874b)

![image](https://github.com/user-attachments/assets/f0841804-f369-46a9-a7ae-0f9ad3fbd540)

![image](https://github.com/user-attachments/assets/cff290a9-77e5-4632-928a-76c2007592f0)

![image](https://github.com/user-attachments/assets/d5fd7e60-9b54-4c84-8ce5-edd0f09d42ee)

![image](https://github.com/user-attachments/assets/6f5ead30-15c2-44d1-b1a2-e47c6311487b)

![image](https://github.com/user-attachments/assets/9c272f49-257c-449f-bac9-224a23f1b8c8)

![image](https://github.com/user-attachments/assets/5c6e7e1e-9bdd-4428-a956-d0c1f73c3435)

![image](https://github.com/user-attachments/assets/4cbd5813-aa98-4af3-b790-c2f901479fab)

<p>
<br> Part 3 (Observe SSH Traffic) </b>
  <br> - Back in Wireshark, I filtered for SSH traffic only </b>
  <br> - From the Windows 10 VM (VM1), I “SSH'ed” into the Ubuntu Virtual Machine (VM2) (via its private IP address) with the user "labuser"
  </b>
  <br> - Typed commands (username, pwd, etc) into the linux SSH connection and observed SSH traffic spam in WireShark
 </b>
 <br> - Exited the SSH connection by typing ‘exit’ and pressing [Enter]
 </b>
</p>

![image](https://github.com/user-attachments/assets/1adbe6c4-81c3-46c0-8ecd-88f42b27751d)

