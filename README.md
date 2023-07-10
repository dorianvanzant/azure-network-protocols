<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDP, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create two virtual machine within Azure
- Step 2
- Step 3
- Step 4

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Azure Virtual Images"/>
</p>
<p>
Create a Windows 10 VM and an Lunix (Ubuntu) VM under the same resource group and virtual network.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install Wireshark on the Windows 10 VM. Open Wireshark and filter for ICMP traffic only. Ping the private IP address of the Ubuntu VM and observe the requests and replies within Wireshark. Attempt to ping a public website and observe the traffic. Open the NSG of your Ubuntu VM and disable inbound ICMP traffic and try to ping it from the Windows VM; take note of the affects it has on the attempt. Re-enable inbound ICMP traffic, ping it again, and note the changes.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
In Wireshark, filter for SSH traffic only. SSH into your Ubuntu Virtual Machine using its private IP address and try some commands and observe SSH traffic in Wireshark. Exit the SSH connection by typing "exit" and pressing [Enter]
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
In Wireshark, filter for DHCP traffic only. Attempt to issue your VM a new IP address from the command line (ipconfig/renew) and observe the DHCP traffic in Wireshark.
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
In Wireshark, filter for DNS traffic only. Use nslookup to see what google.com and disney.com's IP addresses are and observe the DNS traffic in Wireshark.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
In Wireshark, filter for RDP traffic only (tcp.port == 3389) and observe the traffic. The reason there's immediate non-stop traffic is because RDP is constantly showing a live stream from one computer to another, therefore traffic is always being transmitted.
</p>
<br />















