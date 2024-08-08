# Network-Security-Groups-NSGs-and-Inspecting-Traffic-Between-Azure-Virtual-Machines<p align="center">
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

- Create Microsoft Azure subscription
- Create two virtual machines(VM) in Azure, with one VM running Windows 10 and the other running Ubuntu/Linux 
- Download Wireshark (Protocol Analyzer)
- Monitor traffic between the two virtual machines using WireShark

<h2>Actions and Observations</h2>

<p>
<img src="https://imgur.com/bpheUCG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The image above is an example of two virtual machines(VM) that have been created in Microsoft Azure. Notice VM1 is running Windows and VM2 is running Ubuntu/Linux.    
</p>
<br />

<p>
<img src="https://imgur.com/DYBgJkO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The image above is using WireShark to monitor a filtered Internet Control Message Protocol(ICMP) ping between VM1(10.0.05) and VM2(10.0.04). Windows PowerShell was used to ping between the two virtual machines.
</p>
<br />

<p>
<img src="https://imgur.com/hpQ8Peg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In the image above an inbound security rule is being added to deny any incoming ICMP ping to VM2. Essentinally a firewall is being created in Azure for the VM2 network security group, to deny incoming ping.
</p>
<br />


<img src="https://imgur.com/KWWO8f0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The image above shows the result of the inbound security rule being set for VM2 to deny any incoming ICMP ping. Notice VM1(10.0.05) no longer gets a response from VM2(10.0.04)
