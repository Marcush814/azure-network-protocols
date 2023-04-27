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

***Observe SSH Traffic:***

To SSH in (EX: Labuser@10.0.0.6) Its the username for your VM-Ubuntu and the Private IP address for Ubuntu, then it will ask for the password. It wont visually appear so try your best when trying to login to it. Make sure to exit by simply typing "exit" to end the connection.

</p>
<br />

<p>
<img src="https://i.imgur.com/sfAbQTr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

***Observe DHCP Traffic:***

We will filter for DHCP Traffic only and in the command line type ipconfig /renew to attempt to issue our VM a new IP address.

</p>
<br />

<p>
<img src="https://i.imgur.com/tKjviov.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

***Observe DNS Traffic:***

From your Windows 10 VM in the comman line type nslookup followed by google.com or disney.com to see their IP addresses.

</p>
<br />

<p>
<img src="https://i.imgur.com/1nUZOOV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

***Observe RDP Traffic:***

In WireShark filter for RDP only (tcp.port==3389)

It will spam traffic non-stop because RDP is constantly showing you live stream from one computer to another.

</p>
<br />

<p>
<img src="https://i.imgur.com/yoSTeFy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

***This concludes my tutorial of Network Security Protocols and observing traffic between virtual machines.***

</p>
<br />

