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

<p> Create a Resource Group in Azure

Create a Windows 10 Virtual Machine (VM)

Use 2-4 Virtual CPUs.
Allow it to create a new Virtual Network (Vnet)creating a name, username and password of your choosing.
</p>
<br />
</p>

![image](https://github.com/user-attachments/assets/85c12ae6-002d-4179-af2d-82178405ee57)

<p>
</p>

</p>
<br />

## Part 2: Installation

1. **Create an Azure Virtual Machine Windows 10, 4 vCPUs**
   - **Name**: `Vm-osticket`
   - **Username**: `labuser` (example)
   - **Password**: `osTicketPassword1!` (example)

2. **Download Installation Files**
   
   these are files used to install osTicket and some of the depencies
   
   - [osTicket Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)

<br />

      

![image](https://github.com/user-attachments/assets/f148f28e-0008-4ce3-bd48-1755b6093d7a)


 
   <br />
   Go back to the Virtual Machine you just created and copy the Public IP address.  Once you have the IP address go to the Start Menu type in Remote desktop Connection , paste the Public IP address there and log in with the same credentials you used to create the Virtual Machine. Once you have the remote desktop connection open you want to open up microsoft edge and paste the URL (installation file). Right click the start menu icon search for Run and then type in Control . Search for Programs then program/ features (control panel to install/enable IIS.)
   
**Install / Enable IIS in Windows with the following features**:
   - **CGI and Common HTTP Features**
   - **World Wide Web Services -> Application Development Features ->**
     - [X] CGI
     - [X] Common HTTP Features
   - **Internet Information Services -> Web Management Tools -> IIS Management Console**
     - [X] IIS Management Console

![image](https://github.com/user-attachments/assets/509789f1-fb69-4ea0-b3cd-e9e5c3bbdc8e)

![image](https://github.com/user-attachments/assets/629f09bc-3a4f-462f-8cd4-56990be7505e)


![image](https://github.com/user-attachments/assets/edeece72-29f2-4a9f-b648-25c2044875d0)


Enable and Expand the following features

![image](https://github.com/user-attachments/assets/4f1469a1-448a-4604-be19-9536750a0be9)


Once youve selected the features and click okay it will install IIS which is the web serving that osTicket runs on. 
**NOTE: To test if the changes were applied succesfully, type "127.0.0.1" on your browser and this page below should appear.**
</p>

![image](https://github.com/user-attachments/assets/693742a2-e72a-4c35-8f79-93cb49f229d7)

<br />

 **From the Installation Files, download and install the following**:
   - **PHP Manager for IIS**: `PHPManagerForIIS_V1.5.0.msi`
   - **Rewrite Module**: `rewrite_amd64_en-US.msi`

 
 ![image](https://github.com/user-attachments/assets/c1ab67ab-6704-4be7-8c06-d80ce18f8df2)
 
![image](https://github.com/user-attachments/assets/ec5b1ed2-e76f-44d4-abca-2645e8210e6b)

 **Create the directory `C:\PHP`**
From File Explorer you will then create the directory in "C:" naming the new folder "PHP"


![image](https://github.com/user-attachments/assets/25f8aa42-d134-4a0e-b69c-42a962dc83ef)

 
 
 **Download and install PHP 7.3.8**:
   - **File**: `php-7.3.8-nts-Win32-VC15-x86.zip`
   - **Unzip** the contents into `C:\PHP`


     ![image](https://github.com/user-attachments/assets/336f241b-cb17-4a6f-b9ff-88c197cb859f)



 **Download and install VC_redist.x86.exe**

 **Download and install MySQL 5.5.62**:
   - **File**: `mysql-5.5.62-win32.msi`
   - **Typical Setup**
   - **Launch Configuration Wizard (after install) ->**
   - **Standard Configuration**
   - **Password**: `Password1`


     ![image](https://github.com/user-attachments/assets/1d551b86-8f64-4dfb-b5ca-2a2c6f3c551a)


 **Open IIS as an Admin**
  search IIS in the Windows search bar, right click- open as administrator

  
 **Register PHP from within IIS**

 ![image](https://github.com/user-attachments/assets/c1f006f5-d144-4035-ba35-6b23e89eb5c8)


 **Reload IIS (Open IIS, Stop and Start the server)**

 **Install osTicket v1.15.8**:
    - Download osTicket from the Installation Files Folder.
    - Extract and copy the “upload” folder to `C:\inetpub\wwwroot`.
    - Within `C:\inetpub\wwwroot`, rename “upload” to “osTicket”.


Download and install osTicket v1.15.8 from the installation files and extract the contents to c:\inetpub\wwwroot

Within c:\inetpub\wwwroot, Rename “upload” to “osTicket” . Restart the IIS again
   
![image](https://github.com/user-attachments/assets/ea4e3b58-6ce6-4883-bfa6-c360247e63a8)

 **Reload IIS (Open IIS, Stop and Start the server)**
 
![image](https://github.com/user-attachments/assets/08ae7358-42e3-4757-ba25-5a926360500c)

 **Go to sites -> Default -> osTicket**:
    - On the right, click “Browse *:80”.

15. **Enable PHP Extensions**:
    - **Back to IIS, sites -> Default -> osTicket**
    - Double-click PHP Manager.
    - Click “Enable or disable an extension”.
    - Enable: `php_imap.dll`, `php_intl.dll`, `php_opcache.dll`.
    - Refresh the osTicket site in your browser and observe the changes.
   
      
![image](https://github.com/user-attachments/assets/98fdb420-3ea2-4855-bff5-3525d4604cef)


![image](https://github.com/user-attachments/assets/bd9b8caa-6247-4b04-beef-39aae037f660)


 **Rename `ost-config.php`**:
    - From: `C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php`
    - To: `C:\inetpub\wwwroot\osTicket\include\ost-config.php`


![image](https://github.com/user-attachments/assets/8a2f3797-0a51-435f-ab52-15904a413f53)


 **Assign Permissions to `ost-config.php`**:
    - Disable inheritance -> Remove All.
    - New Permissions -> Everyone -> All.


![image](https://github.com/user-attachments/assets/93be7cc8-9080-4e02-9b8b-fc3f5041b9f1)


 **Continue Setting up osTicket in the browser**:
    - **Name**: Helpdesk
    - **Default email**: (receives email from customers)

    
 ![image](https://github.com/user-attachments/assets/57f5c1bb-3907-40cf-af95-19dee5937875)


 **Download and install HeidiSQL from the Installation Files**

 **Open HeidiSQL**:
 
 Open Heidi SQL and create a new session. Make sure to fill in the username as root and create a password. After filling up your credentials now click open and a new session should show up
   
- Create a new session, `root/Password1`.
    - Connect to the session.
    - Create a database called `osTicket`.


![image](https://github.com/user-attachments/assets/2ffc1f29-d5a1-496d-91d3-b0a9db623535)


 **Continue Setting up osTicket in the browser**:
    - **MySQL Database**: `osTicket`
    - **MySQL Username**: `root`
    - **MySQL Password**: `Password1`
    - Click “Install Now!”
    
![image](https://github.com/user-attachments/assets/ced4553b-9a98-46cf-97d7-4ebaefb8205b)

 **Congratulations!! 🎉 you just installed osTicket** 🥳 🥳 🥳
    - Browse to your help desk login page: `http://localhost/osTicket/scp/login.php
