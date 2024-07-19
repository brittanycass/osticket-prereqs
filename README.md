# osticket-prereqs
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>
Before you begin, ensure you have the following:

1. Azure Account: You need an active Azure subscription to create and manage resources.
2. Remote Desktop Client: To connect to the Windows VM in Azure.
3. osTicket Installation Files: Download from Google Drive.
   
Table Of Contents 

.  Create a Virtual Machine in Azure

.  Installation

.  Clean Up 
 
<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>Part 1 (Create Virtual Machine in Azure by going to https://portal.azure.com/.Set up the virtual machine with Windows 10 Pro. Be sure to create a Windows 10 Virtual Machine (VM) with 2-4 Virtual CPUs. When creating the VM, allow it to create a new Virtual Network (Vnet)creating a name, username and password of your choosing.
</p>
<br />
2) Once you have created your virtual machine you will want to connect to it by using the public IP address the vm is set up with. You will connect using the remote desktop connection application.
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
3) Once you have connected to your virtual machine you will go to Control Panel and from there you will open up Programs. Select turn Windows features on and off
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
4) You will want to install/ enable IIS in Windows with CGI and Common HTTP Features
<br />
   World Wide Web Services-> Application Development Features-> [X] CGI [X] Common HTTP Features
   
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
