<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


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

- Step 1 (Create our Resources)
- Step 2 (Observe ICMP Traffic)
- Step 3 (Observe SSH Traffic)
- Step 4 (Observe DHCP Traffic)
- Step 5 (Observe DNS Traffic)
- Step 6 (Observe RDP Traffic)

<h2>Actions and Observations</h2>

<p>

Step 1 (Create our Resources)

</p>

<p>
(Create our Resources)
  
1) Create a Resource Group

<img src="https://i.imgur.com/pQcowOd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

2) Create a Windows 10 Virtual Machine (VM)
    - While creating the VM, select the previously created Resource Group
    - While creating the VM, allow it to create a new Virtual Network (Vnet) and Subnet

<img src="https://i.imgur.com/QQejDSJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

3) Create a Linux (Ubuntu) VM
    - While create the VM, select the previously created Resource Group and Vnet

<img src="https://i.imgur.com/VPlWuFv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

4) Observe Your Virtual Network within Network Watcher
</p>

<br />

<p>
Step 2 (Observe ICMP Traffic)
  
</p>

<p>
  
5) Use Remote Desktop to connect to your Windows 10 Virtual Machine

<img src="https://i.imgur.com/4IpzCav.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/JgbngY1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

6) Within your Windows 10 Virtual Machine, Install Wireshark

<img src="https://i.imgur.com/JaUdJrX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  
7) Open Wireshark and filter for ICMP traffic only

<img src="https://i.imgur.com/JxjJqRf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/j3Rta4P.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


8) Retrieve the private IP address of the Ubuntu VM and attempt to ping it from within the Windows 10 VM
   
   - Observe ping requests and replies within WireShark

<img src="https://i.imgur.com/iNG8h34.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/4dKx5Uf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
     
9) From The Windows 10 VM, open command line or PowerShell and attempt to ping a public website (such as www.google.com) and observe the traffic in WireShark

<img src="https://i.imgur.com/TnWW8ds.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

10) Initiate a perpetual/non-stop ping from your Windows 10 VM to your Ubuntu VM

<img src="https://i.imgur.com/Bet9tYG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   
  - Open the Network Security Group your Ubuntu VM is using and disable incoming (inbound) ICMP traffic

<img src="https://i.imgur.com/knOTIVS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/skXmNXb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/qS6UnEy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

  - Back in the Windows 10 VM, observe the ICMP traffic in WireShark and the command line Ping activity

    - Re-enable ICMP traffic for the Network Security Group your Ubuntu VM is using

<img src="https://i.imgur.com/UPhbDps.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/wGSsgnX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

  - Back in the Windows 10 VM, observe the ICMP traffic in WireShark and the command line Ping activity (should start working)

<img src="https://i.imgur.com/GRz8hqG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

  - Stop the ping activity 
</p>

<br />
<p>

Step 3 (Observe SSH Traffic)

<img src="https://i.imgur.com/zMh9Hix.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  


11) Back in Wireshark, filter for SSH traffic only

12) From your Windows 10 VM, “SSH into” your Ubuntu Virtual Machine (via its private      IP address)

  - Type commands (username, pwd, etc) into the linux SSH connection and observe SSH traffic spam in WireShark

  - Exit the SSH connection by typing ‘exit’ and pressing [Enter]

</p>


<p>
  
Step 4 (Observe DHCP Traffic)

11) Back in Wireshark, filter for SSH traffic only

12) From your Windows 10 VM, “SSH into” your Ubuntu Virtual Machine (via its private      IP address)

  - Type commands (username, pwd, etc) into the linux SSH connection and observe SSH traffic spam in WireShark

  - Exit the SSH connection by typing ‘exit’ and pressing [Enter]

</p>


<p>
  
Step 5 (Observe DNS Traffic)

11) Back in Wireshark, filter for SSH traffic only

12) From your Windows 10 VM, “SSH into” your Ubuntu Virtual Machine (via its private      IP address)

  - Type commands (username, pwd, etc) into the linux SSH connection and observe SSH traffic spam in WireShark

  - Exit the SSH connection by typing ‘exit’ and pressing [Enter]
</p>


<p>
  
Step 6 (Observe RDP Traffic)

11) Back in Wireshark, filter for SSH traffic only

12) From your Windows 10 VM, “SSH into” your Ubuntu Virtual Machine (via its private      IP address)

  - Type commands (username, pwd, etc) into the linux SSH connection and observe SSH traffic spam in WireShark

  - Exit the SSH connection by typing ‘exit’ and pressing [Enter]
</p>

<br />
