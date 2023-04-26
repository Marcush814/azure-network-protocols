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

- Create Resources
- Observe ICMP Traffic
- Observe SSH Traffic
- Observe DHCP Traffic
- Observe DNS Traffic
- Observe RDP Traffic

<h2>Actions and Observations</h2>

***Setup Virtual Environment***

<p>
<img src="https://i.imgur.com/nFOM1RM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
  
***Create a VM using Windows 10 and the other Ubuntu Server:***
 
</p>
<br />

<p>
<img src="https://i.imgur.com/w7vYy1q.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/641qRLS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
***Observe Virtual Network***

</p>
<br />

<p>
<img src="https://i.imgur.com/nB11Tya.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
***Observe ICMP Traffic***
  
  Remote into Windows 10 VM and install WireShark, open it and filter ICMP Traffic. If your using Mac you have to download Microsoft desktop from the app store.
  
  Retrieve the private IP address from Ubuntu Server VM and ping it within WireShark.
  
</p>
<br />

<p>
<img src="https://i.imgur.com/CZjhik9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
***Attempt to ping a public website***
  
</p>
<br />

<p>
<img src="https://i.imgur.com/ME5wAbK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
***Initiate a perpetual ping (ping -t) a non stop ping from VM Windwos 10 to Ubuntu VM:***
  
  To stop the ping press ctrl c
  
</p>
<br />

<p>
<img src="https://i.imgur.com/U6bb9da.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
***Open Network Security Group from Ubuntu and disable ICMP Traffic and observe traffic in WireShark:***
  
  Make sure to change priority to 200 from 310, if not it will put other priorities before it.
  
</p>
<br />

<p>
<img src="https://i.imgur.com/3M6blWk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/1rWxKQT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
