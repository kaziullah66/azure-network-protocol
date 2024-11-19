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
<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462546698_1532769527599755_5436332455491231297_n.png?_nc_cat=105&ccb=1-7&_nc_sid=9f807c&_nc_ohc=Y2Wp9RkLZJQQ7kNvgFbo_nj&_nc_zt=23&_nc_ht=scontent-lga3-2.xx&oh=03_Q7cD1QF-cnQjqWVjjb-j-4X1Ts82OkGIeTVG3INkVO6Ey1HPOg&oe=676400DB"/>
</p>
<p>
We created a Linux and a Windows virtual machine on the same network so we could observe traffic between each other. 
</p>
<br />
<br />
<p>
<img src="https://scontent-lga3-1.xx.fbcdn.net/v/t1.15752-9/462547701_865569982375316_464831406093664846_n.png?_nc_cat=108&ccb=1-7&_nc_sid=9f807c&_nc_ohc=YsaV1F16og0Q7kNvgGmumIp&_nc_zt=23&_nc_ht=scontent-lga3-1.xx&oh=03_Q7cD1QHVuTJXMgWRWBjA4P_dN5wpOydKs8x8a4N4aA4NndfQyg&oe=6763F4E6"/>
<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462542524_1405934143699130_2291762641591403772_n.png?_nc_cat=100&ccb=1-7&_nc_sid=9f807c&_nc_ohc=vxrUfFTHBR0Q7kNvgFzLxUX&_nc_zt=23&_nc_ht=scontent-lga3-2.xx&oh=03_Q7cD1QFnycM_l89fxzaQVh0PTBDSLiRVDsfv38PDTVIcaHDhTw&oe=6763EFBF"/>
</p>
<p>
We downloaded Wireshark, a protocol analyzer, and started observing traffic on the computer.
</p>
<br />
<br />
<p>
<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462041292_1078707823865198_7710343445828787921_n.png?_nc_cat=105&ccb=1-7&_nc_sid=9f807c&_nc_ohc=mk00slwpC5gQ7kNvgGOuf4t&_nc_zt=23&_nc_ht=scontent-lga3-2.xx&oh=03_Q7cD1QGQjxBIMisHgTrbICxzY4SNeH9buyaRIUT6MIhy87LTgw&oe=6763E323"/>
</p>
<p>
We filtered for ICMP traffic, initiated a perpetual ping, and started receiving replies from the Linux virtual machine. 
</p>
<br />
<br />
<p>
<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462543021_1616316085945696_4570867840570373192_n.png?_nc_cat=105&ccb=1-7&_nc_sid=9f807c&_nc_ohc=2Y19ZGUNSSgQ7kNvgFGKj6z&_nc_zt=23&_nc_ht=scontent-lga3-2.xx&oh=03_Q7cD1QFnUJrIkHAL2RGktsQ0XlDSxyZrEvNBVEMzsLD8UrLX1w&oe=6764053A"/>

<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462567831_552622970489830_6102310246806097682_n.png?_nc_cat=101&ccb=1-7&_nc_sid=9f807c&_nc_ohc=irtv4HahZG8Q7kNvgEUiwHI&_nc_zt=23&_nc_ht=scontent-lga3-2.xx&oh=03_Q7cD1QEPcjF8KhAkoTbJIKBQkO0RuvlEW-T_5BL27HfZ9RuMuA&oe=6763DA45"/>

</p>
<p>
We created an inbound port rule for our Linux virtual machine in Azure to deny incoming requests. We see that the requests are now timing out and being ignored.
</p>
<br />
<br />
<p>
<img src="https://scontent-lga3-2.xx.fbcdn.net/v/t1.15752-9/462639026_1085569749852165_3156622879168093775_n.png?_nc_cat=101&ccb=1-7&_nc_sid=9f807c&_nc_ohc=0hJVwVhAgl8Q7kNvgEQsxaT&_nc_zt=23&_nc_ht=scontent-lga3-2.xx&oh=03_Q7cD1QGG77i8q-oHZGdM6zH3nqSjhvpftvxAZSXgzqPl43thLw&oe=6764012A"/>
</p>
<p>
We connected to our Linux virtual machine and filtered for SSH. 
</p>
<br />
<br />
<p>
<img src="https://scontent-lga3-1.xx.fbcdn.net/v/t1.15752-9/462539840_1050355300170841_2499457334563325859_n.png?_nc_cat=102&ccb=1-7&_nc_sid=9f807c&_nc_ohc=hO7r6llBqMMQ7kNvgHqjQJ2&_nc_zt=23&_nc_ht=scontent-lga3-1.xx&oh=03_Q7cD1QGDAexIJwNvVtDxAjxJHgd-0Te4_E5CWzKIj1VW31Zzqg&oe=6763EFBD"/>
</p>
<p>
We filtered for DNS. 
</p>
<br />
<br />
<p>
<img src="https://scontent-lga3-1.xx.fbcdn.net/v/t1.15752-9/462540281_556518583724149_4773454699472645203_n.png?_nc_cat=103&ccb=1-7&_nc_sid=9f807c&_nc_ohc=PO8nzYZQC-UQ7kNvgFlWQcC&_nc_zt=23&_nc_ht=scontent-lga3-1.xx&oh=03_Q7cD1QF1GSeD-E1JzPOfQxu6D4uEGkACogoW_reUE1DRh8rNxw&oe=6763F631"/>
</p>
<p>
We filtered for RDP. 
</p>
<br />





