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

- Create 2 VM's on Azure
- Login to both VM's using remote desktop
- Download wireshark on 1 of the VM's
- Use wireshark to observe the traffic between the 2 VM's using different command lines and protocols

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/9RazVgO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The virtual machines created on Azure, for the purpose of the exercise, were put on the same virtual network and virtual subnet.
</p>
<br />

<p>
<img src="https://i.imgur.com/Ec8NVnG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Observing traffic between both VM's using wireshark. I actually tried pinging VM-2 from VM-1 on powershell and I got a reply because they are on the same virtual network. The next step was to stop ICMP traffic coming from VM-1 into VM-2 and observe on wireshark. This was attempted after executing a perpetual ping as seen in the picture above.
</p>
<br />

<p>
<img src="https://i.imgur.com/QJfPca9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
This is the Azure setting for denying ICMP traffic from one VM to another. And after adding this setting, the perpetual ping stopped and it was on a perpetual request time out.
</p>
<br />
