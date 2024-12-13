<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Deployment and Configuration Steps</h2>

<p>
  <strong>1. Setup a Domain Controller in Azure:</strong><br>
  - Create a domain controller virtual machine and name it DC-1.<br>
  - For Image, select Windows Server 2022. Choose a VM size with at least 2 vCPUs.<br>
  - Proceed to Review + Create and click Create.
</p>

<p>
  <img src="https://i.imgur.com/cf7tWnG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
  <strong>2. Set the Domain Controller’s NIC Private IP address to Static:</strong><br>
  - Go to Virtual Machines and click on DC-1.<br>
  - Select Networking and click on Network Settings.<br>
  - Click on Network interface / IP configuration located at the top.<br>
  - Click on ipconfig1 located at the bottom.<br>
  - For Private IP address settings, set the Allocation to Static and click Save.
</p>

<br>

<p>
  <img src="https://i.imgur.com/CLOUkAK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
  <strong>3. Disable the Domain Controller's Windows Firewall:</strong><br>
  - Log into the DC-1 VM.<br>
  - Once logged in, open the Run dialog box and open wf.msc to open Windows Firewall.<br>
  - Click on Windows Defender Firewall Properties.<br>
  - For each of the three profiles, set the Firewall state to Off and click OK. 
</p>

<br>

<p>
  <img src="https://i.imgur.com/kwDnI7N.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
  <strong>4. Setup a Client in Azure:</strong><br>
  - Create a client virtual machine and name it Client-1<br>
  - For Image, select Windows 10 Pro. Choose a VM size with at least 2 vCPUs.<br>
  - Be sure to select the same region and Virtual Network that the DC-1 virtual machine is in.<br>
  - Proceed to Review + Create and click Create.
</p>

<br>

<p>
  <img src="https://i.imgur.com/Y2RDfRR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
  <strong>5. Set Client-1’s DNS settings to DC-1’s Private IP address:</strong><br>
  - Go to Virtual Machines and click on Client-1.<br>
  - Select Networking and click on Network Settings.<br>
  - Click on Network interface / IP configuration located at the top.<br>
  - Under Settings on the left, click on DNS servers.<br>
  - Select Custom.<br>
  - In Add DNS server, paste DC-1's private IP address and click Save at the top.
</p>

<p>
  <img src="https://i.imgur.com/ha51LRu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
