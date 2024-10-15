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
- Send out a perpetual ping
- Create an inbound security rule 
- Log on to the Linux virtual machine and filter for SSH on Wireshark
- Filter for DNS
- Filter for RDP

<h2>Actions and Observations</h2>

<p>
<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462546698_1532769527599755_5436332455491231297_n.png?_nc_cat=105&ccb=1-7&_nc_sid=9f807c&_nc_ohc=kXqqR6QYVn4Q7kNvgF2R4Dr&_nc_ht=scontent-lga3-2.xx&_nc_gid=Ar-jMIxPTT1EdEThrkPaJz4&oh=03_Q7cD1QGztmvwvKUf784jEsTam2t5s96y9CyntCylUtQRuvHZmA&oe=6733395B" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
We created a Linux and a Windows virtual machine on the same network so we could observe traffic. 
</p>
<br />

<p>
<img src="https://scontent.xx.fbcdn.net/v/t1.15752-9/462547701_865569982375316_464831406093664846_n.png?_nc_cat=108&ccb=1-7&_nc_sid=0024fc&_nc_ohc=NcmCIA2voJQQ7kNvgHlei7x&_nc_ad=z-m&_nc_cid=0&_nc_ht=scontent.xx&_nc_gid=A_habXvldgvuLwKZaDX7U93&oh=03_Q7cD1QFkDRCSvh5N3pR2ygeLLMkh-iGfaLexWogX7dA4uqSTug&oe=67332D66"/>
<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462542524_1405934143699130_2291762641591403772_n.png?_nc_cat=100&ccb=1-7&_nc_sid=9f807c&_nc_ohc=mILDAqVf3VAQ7kNvgH9YzXW&_nc_ht=scontent-lga3-2.xx&_nc_gid=A9TRwuGQcF22EV-CEymANH6&oh=03_Q7cD1QGUb-AEX0zTBYnOSx3D39qCApF09mBNqUwjDmknXdKygg&oe=6733283F"/>
</p>
<p>
We downloaded Wireshark, a protocol analyzer, and started observing traffic on the computer.
</p>
<br />

<p>
<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462041292_1078707823865198_7710343445828787921_n.png?_nc_cat=105&ccb=1-7&_nc_sid=9f807c&_nc_ohc=jPaKa8WiX2wQ7kNvgHUjjPP&_nc_ht=scontent-lga3-2.xx&_nc_gid=AknKDGaSMPzMxIs6m2zFGQv&oh=03_Q7cD1QG2x8ljNMoSGaVja6HsDoV8jeyreMvSB4eBf6J0Lkmg5w&oe=673353E3"/>
</p>
<p>
We filtered for ICMP traffic, initiated a perpetual ping, and started receiving replies from the Linux virtual machine. 
</p>
<br />

<p>
<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462543021_1616316085945696_4570867840570373192_n.png?_nc_cat=105&ccb=1-7&_nc_sid=9f807c&_nc_ohc=NdPEFi3Z3lgQ7kNvgEvuYk2&_nc_ht=scontent-lga3-2.xx&_nc_gid=ASJlsmJFniigreI5skKyyu4&oh=03_Q7cD1QHMGnZgzPk5upi7CD57GTN4HbDy2m0Jgs4VnajorX0Bcg&oe=67333DBA"/>

<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462567831_552622970489830_6102310246806097682_n.png?_nc_cat=101&ccb=1-7&_nc_sid=9f807c&_nc_ohc=YnHwbvvURNMQ7kNvgHFW9dU&_nc_ht=scontent-lga3-2.xx&_nc_gid=AX4KhUkcdsIG868Ji_ZAveV&oh=03_Q7cD1QG2RLf7ygG7ygNDcSTOeZpE7AohK5uUUpY9E444y_i2dg&oe=67334B05"/>

</p>
<p>
We created an inbound port rule for our Linux virtual machine in Azure to deny incoming requests. We see that the requests are now timing out and being ignored.
</p>
<br />


<p>
<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462639026_1085569749852165_3156622879168093775_n.png?_nc_cat=101&ccb=1-7&_nc_sid=9f807c&_nc_ohc=EJtMqOO3mB0Q7kNvgFLqBnQ&_nc_ht=scontent-lga3-2.xx&_nc_gid=ANZkkAN6lGuj11HiKzAubIr&oh=03_Q7cD1QHDWVPHHlU8QhnMe56rfaLfLWdXLGkfYdO9FK64dcu7NA&oe=6734FBAA"/>
</p>
<p>
We connected to our Linux virtual machine and filtered for SSH. 
</p>
<br />

<p>
<img src="https://scontent-lga3-1.xx.fbcdn.net/v/t1.15752-9/462539840_1050355300170841_2499457334563325859_n.png?_nc_cat=102&ccb=1-7&_nc_sid=9f807c&_nc_ohc=NdhcGkN1veQQ7kNvgGLSg5u&_nc_ht=scontent-lga3-1.xx&_nc_gid=AaAaEIdQiNam4YE_ZM3ed0M&oh=03_Q7cD1QFayGGyexi3A9APUGfAnsVJBpzC7uCo_rHE2Bkm7kHkwQ&oe=6735227D"/>
</p>
<p>
We filtered for DNS. 
</p>
<br />
<p>
<img src="https://scontent-lga3-1.xx.fbcdn.net/v/t1.15752-9/462540281_556518583724149_4773454699472645203_n.png?_nc_cat=103&ccb=1-7&_nc_sid=9f807c&_nc_ohc=FKDA7piLw2sQ7kNvgG2F7n7&_nc_ht=scontent-lga3-1.xx&_nc_gid=A-36XImvw4MaPyR_7jzt4RD&oh=03_Q7cD1QGIKzQ4U6j34kGtetV0bcb3DmyjqBuQKVtKsM5dDkUAXA&oe=673528F1"/>
</p>
<p>
We filtered for RDP. 
</p>
<br />





