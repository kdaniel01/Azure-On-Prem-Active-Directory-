<h1>Azure On-premises Active Directory Project</h1>


<h2>Description</h2>
<img src="https://i.imgur.com/gpAAUq4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<b>In this project,I deployed and configured an On premises Active Directory in Microsoft Azure using Virtual Machines.
</b>


<h2>Environments and Technologies Used</h2>

- <b>Azure Virtual Machine (Windows Server 2022)<br /> 
- <b>Azure Virtual Machine (Windows 10 21H2)<br />
- <b>Active Directory Domain Services<br />
- <b>Powershell<br />

<h2>Overview </h2>
- <b>Deploying Resources in Azure<br /> 
- <b>Checking for connectivity between Client Virtual Machines and Domain Controller<br />
- <b>Installing Active Directory and Admin Creation<br />



<h2>Part 1- Deploying Resources in Azure:</h2>

<p align="center">
Deployed a Windows Server 2022 Virtual Machine with was used as the Domain Controller named "DCvm1".The DC's NIC Private address was set to static - Networking> NIC> Ip config: <br/>
<img src="https://i.imgur.com/QOK5OR4.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
A Created a Client VM named "Clientvm1" which was deployed in the same resource group as the Domain COntroller "DCvm1". Both VMs were also deployed in the same Virtual Network<br/>
<img src="https://i.imgur.com/iqYwAfX.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
<h2>Part 2- Checking for connectivity between Client Virtual Machines and Domain Controller:</h2>
Logged into Clientvm1 using RDP and attempted to ping the DCvm1's private IP which was unsuccessful as shown below.It failed because no Inbound ICMPv4 rule was created to allow this.<br/>
<p align="center">
<img src="https://i.imgur.com/TEszJLO.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p align="center">
ICMPv4 Inbound rule was created on DCvm1 <br/>
<img src="https://i.imgur.com/EWkJYcR.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/> <br />
<img src="https://i.imgur.com/xgR1w58.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<p align="center">
Retried pinging the Domain Controller which was successful confirming connectivity.<br/>
<img src="https://i.imgur.com/XaAkgTX.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<h2>Part 3- Installing Active Directory and Admin Creation:</h2>
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
