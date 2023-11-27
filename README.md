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

<h2>Actions and Observations</h2>

<p>

Step 1 (Create our Resources)
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
(Create our Resources)
  
1) Create a Resource Group
2) Create a Windows 10 Virtual Machine (VM)
    - While creating the VM, select the previously created Resource Group
    - While creating the VM, allow it to create a new Virtual Network (Vnet) and Subnet
3) Create a Linux (Ubuntu) VM
    - While create the VM, select the previously created Resource Group and Vnet
4) Observe Your Virtual Network within Network Watcher

</p>

<br />

<p>
Step 2 (Observe ICMP Traffic)
  
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
  
5) Use Remote Desktop to connect to your Windows 10 Virtual Machine

6) Within your Windows 10 Virtual Machine, Install Wireshark
  
7) Open Wireshark and filter for ICMP traffic only
  
8) Retrieve the private IP address of the Ubuntu VM and attempt to ping it from within the Windows 10 VM
   
   - Observe ping requests and replies within WireShark
     
9) From The Windows 10 VM, open command line or PowerShell and attempt to ping a public website (such as www.google.com) and observe the traffic in WireShark

10) Initiate a perpetual/non-stop ping from your Windows 10 VM to your Ubuntu VM

    - Open the Network Security Group your Ubuntu VM is using and disable incoming (inbound) ICMP traffic
    - Back in the Windows 10 VM, observe the ICMP traffic in WireShark and the command line Ping activity
    - Re-enable ICMP traffic for the Network Security Group your Ubuntu VM is using
    - Back in the Windows 10 VM, observe the ICMP traffic in WireShark and the command line Ping activity (should start working)
    - Stop the ping activity
 
</p>

<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
