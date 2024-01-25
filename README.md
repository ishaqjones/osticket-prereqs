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

1.) To begin this project start by creating a virtual machine in Azure https://portal.azure.com/ . The requirements for the machine are as follows: Windows 10 Pro 22h2 with 2-4 CPUs and 16gb of memory. 

2.) Once created, connect to the virtual machine via the IP address assigned. You will connect via a remote desktop connection app. 
</p>
<br />

<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/b5194208-0026-4537-a83b-303b0b579863)

</p>

<p>
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/ac15f1d5-3b62-429e-b13f-bad08d4aff96)


</p>
<p>
  
3.) Once the connection is established, open your control panel, and select 'programs'. Select 'Turn Windows features on of off. 

<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/ddb8815a-5464-4a7a-8de1-b792a8bb2077)

</p>
<p>
  
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/2fc21dae-1af8-45ae-a15e-b90762b1beae)

</p>
<p>
  
4.) From 'Turn Windows features  On or Off' install/enable IIS Windows with CGI and Common HTTP features. 
   World Wide Web Services -> Application Development Features -> 
   [X] CGI
   [X] Common HTTP Features
  
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/5be33b87-ca46-4c85-a15a-5eb221fdf395)

</p>
<p>
  
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/05b2fa1b-f4c2-41cd-abd6-8eb752b393c9)

</p>
<p>
  
***NOTE*** Make sure all Common HTTP Features are selected.
 
 Confirm IIS is installed/enabled by opening  the  browser and navigating to 127.0.0.1 
  Your results should resemble the image below. 
  
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/344758f2-c7c5-4279-83df-3ec6b0e5b20f)


</p>
<p>
  
  
  
  
5.) IIS is now enabled so we'll down so we'll download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) 
  Using the wizard, we'll complete a default install.
  
6.) Download and install the Rewrite Module (rewrite_amd64_en-US.msi)
  
7.) Create a folder in the C drive and name it PHP.
  
8.)  Download PHP 7.3.8 (php-7.3.88-nts-Win32-VC15-x866.zip) and extract the contents into C:\PHP
  
  !! ATTENTION !!
If this appears, choose to “Keep” the file:
  
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/3d09bd60-27ed-450f-a5eb-33fe73184834)

</p>
<p>
  
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/98590556-1c4a-4d6a-87bf-d11b4f4a22ba)

</p>
<p>

9.) ONce the extracted file is completed download and install the VC_redist.x86.exe. Using the wizard adhere to a default install of VC_redist.x86.exe. 
  
10.) Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
  Run the setup wizard:
-Typical Setup ->
-Launch Configuration Wizard (after install) ->
-Standard Configuration ->

  Make the new root password one you'll remember for instance 'Password1'
  
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/d8b19c89-0549-4602-89db-96e5055987e4)

</p>
<p>
  
  Continue to the next page in the configuration wizard. 
  
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/b39a5140-c6ab-4293-97ba-c087135ab482)

</p>
<p>
  
11.) With the files downloaded and installed, we can now search for IIS in the windows search bar, select it, and open it with Administrative privileges. 
     The results should be similar to the picture below. 
  
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/482592e4-c505-4c7a-8c08-473876013d56)

</p>
<p>
  
12.) From here we'll continue and register PHP with IIS by selecting the PHP Manager.
  
  
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/f3be932a-dfad-4799-8d50-c06d2e158b31)

</p>
<p>
  
Select 'Register New PHP version'.
  
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/579b5b4a-b125-40bc-ac97-c3504793a81b)

</p>
<p>
  
Establish a path to the php executable file (php-cgi.exe). 
  -C Drive -> 
  -PHP -> click on php-cgi file.
  
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/5acbd4fa-374c-47ff-8177-dbd72284123b)

</p>
<p>
  
  Restart the IIS server.
  
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/ef0a0ee3-e1c3-44ac-a57b-5907aed4a760)

</p>
<p>
  
13.) Install osTicket v1.15.8
  -Download osTicket 
  -Extract and copy the "upload" folder to c:\inetpub\wwwroot
  -Within c:\inetpub\root, Rename "upload" to "osTicket"
</p>

<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/7083c2d3-0915-4732-8b98-b156da3f308d)

</p>
  
  Reload IIS again.
  
14.) In IIS go to sites -> Default -> osTicket -> Click “Browse *:80” to the right of the menu
  
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/358f3bb1-8056-4fef-b01e-fe719fe0a76b)

</p>
<p>
  
  **NOTE** some extensions have not been enabled. See below.
  
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/afbd119a-cfe6-473e-86af-47b2740841fb)

</p>
<p>
  
  To enable the extensions:
  -Go back to IIS, sites -> Default -> osTicket
  -Double click PHP manager
  -Click "Enable or disable an extension"
  
<p>
  
 ![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/ee48caad-a8c7-4295-ac5f-68f737544ea7)

</p>
<p>
  
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/38242170-67fc-4f35-bb30-cc173e87d4ca)


</p>
<p>
  
  From this point enable the following extensions.
  
  1.) php_imap.dll
 
  2.) php_intl.dll
  
  3.) php_opcache.dll
  
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/f4913a47-297a-4a8e-9626-1b615a643f32)

</p>
<p>
  
  
15.) Onece the extensions are enabled in IIS, next is the renaming of a file in our osTicket folder. In file explore search C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php.
     Rename ost-sampleconfig.php to ost-config.php.
  
  We are going to rename the ost-sampleconfig.php to ost-config.php

  Next, we will remove all inherited permissions from this object by right-clicking properties, selecting the security tab, advance button, and 'disable inheritance'.
  
  
  From here we'll add new permissions
  
  Click Add
  
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/787a7f4a-ab87-4488-9866-fb4f5a64e22e)

</p>
<p>
  
Select a principal
  
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/39d170fd-cfc4-4ea6-a6bf-d1f23e4421e4)

</p>
<p>
  
  
 Choose the 'Everyone', and 'Check Names' button then select 'Ok'.
  
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/659bff26-b095-4eed-9497-296418acf0bb)

</p>
<p>
  
 Select Full Control complete with additional unchecked options
  
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/b6c617f8-3a6c-4aa8-a0c6-ea3d869a297c)

</p>
<p>
  
  Select Apply then Ok.
  
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/054f1557-6bf4-400d-92ef-9c48feb3b6ce)


</p>
<p>
  
  
 Download and install HeidiSQL. 
  
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/61987a21-fe48-4a5c-aed4-437a9cb4af05)

</p>
<p>
  
  Select the 'New' session in the bottom left corner of the HeidiSQL configuration wizard.
  
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/88ca88b1-a9cf-45de-8b33-6cf6386539b0)

</p>
<p>
  
  Create the username as 'root' with the password as 'Password1'.
  
<p>
  
![image](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/b8cc1f44-1d40-468f-9c2d-107cba726f56)

</p>
<p>
  
 Once connected to the session we'll return to the browser to complete osTcket admin credentials. Complete the Database Settings implementing the root and Password1 credentials.
  
 Continuing we will create a new database in Heidi. To achieve this, right-click  "Unnamed", select "create new", and then select "database". An option will appear to name the database. Name the new database osTicket.
 </p> 
 <p>
   

  ![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/d8b58358-9dd0-4a69-8b70-956c93995475)

  ![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/e9032600-3f1d-4a26-99bb-8ee1bb76eba2)

  
 </p>
  
  Once the new database is set up return to  osTicket in the browser.  Under the MySQL Database specification type 'osTicket'.
  
<p>
  
![alt-text](https://github.com/ishaqjones/osticket-prereqs/assets/156931487/6a07b688-b370-4128-92d4-d5fa345b1d72)

</p>
<p>
  
  The last step is to do some clean up. We will want to delete the setup folder in our system. 
  -Delete: C:\inetpub\wwwroot\osTicket\setup
  Only delete the setup folder and nothing else.
  
  We then will want to set the permissions back to "Read" only in the ost-config.php file.
  
<p>
<img src="https://imgur.com/wFr0pkK.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/jsJOPyn.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  The last step after that is to login to osTicket on the browser.
  
<p>
<img src="https://imgur.com/uHVdDsx.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Congrats! You have now successfully installed and setup osTicket!

