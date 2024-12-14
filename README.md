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
  <strong>1. Install Active Directory:</strong><br>
  - Log into the Domain Controller VM.<br>
  - Click on the Windows Start button and click Server Manager.<br>
  - On the Server Manager Dashboard, click Add roles and features.<br>
  - In the Wizard, click Next until you reach Server Roles.<br>
  - In Server Roles, select Active Directory Domain Services and click Add features.<br>
  - Continue clicking Next until you reach Confirmation.<br>
  - In Confirmation, select Restart, click yes and then click Install.
</p>

<p>
  <img src="https://i.imgur.com/rE0YPdz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
  <img src="https://i.imgur.com/ESpBKYj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
  <img src="https://i.imgur.com/DOorfaz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
  <strong>2. Promote Server to Domain Controller:</strong><br>
  - On the Server Dashboard, click on the Notifications button (flag icon) at the top right and click Promote this server to a domain controller.<br>
  - In Deployment Configuration, select Add a new forest.<br>
  - For the Root domain name, type the domain name you'll be using and then click Next.<br>
  - In Domain Controller Options, confirm the password you'll be using and then click Next.<br>
  - Continue clicking Next in the wizard. For Prerequisites Check click Install.<br>
  - The installation will prompt a restart, which will require reconnecting to the VM via Remote Desktop Connection.
</p>

<br>

<p>
  <img src="https://i.imgur.com/VvHT9tP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
  <img src="https://i.imgur.com/0T81XBV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
  <strong>3. Log back into DC-1:</strong><br>
  - Log into the DC-1 VM using your domain name, backslash(\), your username. 
</p>

<br>

<p>
  <img src="https://i.imgur.com/9j18bmh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
  <strong>4. Create a Domain Admin user within the Domain:</strong><br>
  - Click on the Windows Start button and click Windows Administrative Tools. Select Active Directory Users and Computers.<br>
  - Right-click on the domain name, hover over New and select Organizational Unit.<br>
  - Name the new organizational unit _EMPLOYEES and click OK.<br>
  - Create another organizational unit named _ADMINS.<br>
  - Right-click on the newly created _ADMINS folder, hover over New and select User.<br>
  - Provide the user's full name and logon name. Click Next and provide a password. Click Next and Finish.<br>
  - Right-click on the newly created user within the _ADMINS folder and select Add to a group.<br>
  - In the Enter the object names field, type domain admins and click Check Names. Click OK.
</p>

<br>

<p>
  <img src="https://i.imgur.com/CNglMay.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
  <img src="https://i.imgur.com/3OKiYFF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
  <img src="https://i.imgur.com/tPKS5p8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
  <img src="https://i.imgur.com/32bJI6P.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
  <img src="https://i.imgur.com/8riQ697.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
  <img src="https://i.imgur.com/oFuFEmm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
  <strong>5. Log in with the Newly Created Username:</strong><br>
  - Log out off the DC-1 VM.<br>
  - Log back into DC-1 with the new username: domain name, backslash(\), followed by the logon name created in the previous step.
</p>

<p>
  <img src="https://i.imgur.com/s9Owf3G.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
