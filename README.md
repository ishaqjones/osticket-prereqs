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

- PHP Manager For IIS_V1.5.0.msi
- Rewrite Module (rewrite_amd64_en-US.msi)
- PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip)
- VC_redist.x86.exe
- MySQL 5.5.62 (mysql-5.5.62-win32.msi)
- HeidiSQL
- osTicket v1.15.8

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To begin, create a virtual machine using Azure https://portal.azure.com/. We'll be using Windows 10 v. 22H2. Requirments for the virtual machine are as follows 2 cpus and at least 16gb of memory. 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
When the virutal machines has been created and it running you can establish a connection using the public ip address as supplanted by the virtual machine via remote desktop. 
</p>
<br />

<p>
 
 ![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/4fda4fe1-87f4-409e-ac46-b89b78044471)

</p>
<p>
Next, we'll want to install and enable IIS in Windows with CGI and Common HTTP Features assigned. 
  World Wide Web Service --> Application Development Freatures -->
  [x] CGI
  [x] Common HTTP Console
</p>
<br />
