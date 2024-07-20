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
3. osTicket Installation Files: Download from Google Drive https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6
   
Table Of Contents 

.  Create a Virtual Machine in Azure

.  Installation

.  Clean Up 
 
<h2>Installation Steps</h2> Part 1: Create Virtual Machine in Azure

<p>

<p>Part 1 Create a Resource Group in Azure

Create a Windows 10 Virtual Machine (VM)

Use 2-4 Virtual CPUs.
Allow it to create a new Virtual Network (Vnet)creating a name, username and password of your choosing.
</p>
<br />
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

</p>
<br />
PART 2: Installation
<p>
   Create an Azure Virtual Machine Windows 10, 4 vCPUs
   <br />
Name: Vm-osticket
   <br />
Username: labuser (for example/whatever you chose)
   <br />
Password: osTicketPassword1! (for example/whatever you chose)
<br />
   2. Download the Installation File
   <br />
   https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   <br />
3) You will want to install/ enable IIS in Windows with CGI and Common HTTP Features
<br />
   World Wide Web Services-> Application Development Features-> [X] CGI [X] Common HTTP Features
   AND IIS Management Console
Internet Information Services -> Web Management Tools -> IIS Management Console
	[X] IIS Management Console

   
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
