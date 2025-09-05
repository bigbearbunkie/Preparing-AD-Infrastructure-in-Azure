<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Preparing AD Infrastructure in Azure</h1>
This tutorial outlines the preparation of Azure virtual machines to set up Active Directory.<br />


<h2>Summary</h2>

The objective here is to create two virtual machines: one to run Windows Server and act as a domain controller (DC-1), and another to run Windows 10 and act as a client (Client-1). Then I will join Client 1 to the domain and be able to log in as a user that exists within the domain controller. But first, I will need to change the Domain Controller's NIC Private IP address from Dynamic to Static and disable the Windows Firewall. Then I can change Client-1's DNS settings to DC-1’s Private IP address. I will then use the PowerShell command ping to test the connection.

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 Pro


<h2>Deployment and Configuration Steps</h2>

<h3>Step 1: Create a Resource Group, Virtual Network, and a Subnet</h3>

<p> - From the home screen of Azure, create a new Resource Group and name it "ActiveDirectoryLab". Click "Review and Create". When it's finished, click "Create". </p>

<p>
<img src="https://github.com/bigbearbunkie/Preparing-AD-Infrastructure-in-Azure/blob/main/AD%20prep%20Step%201.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<br />

<p> - Now create a new Virtual Network. Select "ActiveDirectoryLab" for your resource group and name it "ActiveDirectoryVnet". Make sure it is in the same region as your Resource Group. Click "Review and Create". When it's finished, click "Create".</p>

<p>
<img src="https://github.com/bigbearbunkie/Preparing-AD-Infrastructure-in-Azure/blob/main/AD%20prep%20Step%201b.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
<img src="https://github.com/bigbearbunkie/Preparing-AD-Infrastructure-in-Azure/blob/main/AD%20prep%20Step%201c.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<br />

<h3>Step 2: Create two virtual machines: a Domain Controller (DC-1) and a "client" (Client-1)</h3>

<p> - Create a new Virtual Machine. Select "ActiveDirectoryLab" for your resource group and name it "DC-1". Make sure it has the same region as everything else. Select "Windows Server 2022 Datacenter Azure Edition HotPatch - x64 Gen2" as the Image. For the Size, just choose one that has AT LEAST 2 vcpus and 8 GiB memory. Set the Username to "labuser" and the password: "Cyberlab-123". Click the licensing agreements at the bottom and click "Next" twice to get to the "Networking" tab. Select "ActiveDirectoryVnet" for your virtual network and set your subnet to "default".  Click "Review and Create". When it's finished, click "Create".</p>

<p>
<img src="https://github.com/bigbearbunkie/Preparing-AD-Infrastructure-in-Azure/blob/main/AD%20prep%20Step%202.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
<img src="https://github.com/bigbearbunkie/Preparing-AD-Infrastructure-in-Azure/blob/main/AD%20prep%20Step%202b.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
<img src="https://github.com/bigbearbunkie/Preparing-AD-Infrastructure-in-Azure/blob/main/AD%20prep%20Step%202c.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
<img src="https://github.com/bigbearbunkie/Preparing-AD-Infrastructure-in-Azure/blob/main/AD%20prep%20Step%202d.PNG?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
