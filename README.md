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

- Create Windows and Linux virtual machines
- Download a protocol analyzer 
- Filter for ICMP traffic 
- Send out a perpetual ping through the Windows virtual machine and create an inbound security rule in the Linux virtual machine to ignore the ping requests
- Log on to the Linux virtual machine and filter for SSH on Wireshark

<h2>Actions and Observations</h2>

<p>
<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462546698_1532769527599755_5436332455491231297_n.png?_nc_cat=105&ccb=1-7&_nc_sid=9f807c&_nc_ohc=kXqqR6QYVn4Q7kNvgF2R4Dr&_nc_ht=scontent-lga3-2.xx&_nc_gid=Ar-jMIxPTT1EdEThrkPaJz4&oh=03_Q7cD1QGztmvwvKUf784jEsTam2t5s96y9CyntCylUtQRuvHZmA&oe=6733395B" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
We created a Linux and a Windows virtual machine on the same network so we can send and receive traffic. 
</p>
<br />

<p>
<img src="[https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps](https://www.messenger.com/messenger_media/?attachment_id=865569975708650&message_id=mid.%24cAABa9TbkxDCYtzOL12She4SSL1Lw&thread_id=100009234449456)"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
