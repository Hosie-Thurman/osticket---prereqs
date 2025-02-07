
![Image](https://github.com/user-attachments/assets/fff316f9-b508-4214-9019-39caac5db711)
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

- Microsoft Azure
- Virtual Machine
- osTicket Installation Files [link](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)


<h2>Installation Steps</h2>

<h3>Step 1: Access your Virtual Machine via Remote Desktop</h3>
If you're unsure how to connect to your virtual machine, check out my guide here for assistance.

[here](https://github.com/miquelmanaois/virtualmachine)

<h3>Step 2: Install / Enable Internet Information Services (IIS) in Windows</h3>

- Press Windows Key + R
- Type "optionalfeatures in the box

	![Image](https://github.com/user-attachments/assets/b9fee68d-96d0-45b4-bae4-e2aef09beb07)
![Image](https://github.com/user-attachments/assets/c2ef64f5-0450-4c37-81bd-1cf7af415274)

<h3>Step 3:  Downloading the osTicket Installation files</h3>

- osTicket Installation Files [link](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)
	- Unzip the file and Drag and drop the folder to your desktop->
		- You will then follow a prompt to install Web Platform Installer
			- Open Web Platform Installer

![Image](https://github.com/user-attachments/assets/05c613f7-8bf3-42dc-ad3b-5092458f5b1b)
![Image](https://github.com/user-attachments/assets/695bfb24-2040-4fe9-84d8-a569c6d0fbdf)

<h3>Step 3: PHP Manager for IIS</h3>

- Create the directory C:\PHP
- From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder


![Image](https://github.com/user-attachments/assets/b691aa19-250a-4e23-a7a1-66ea7d414ae5)

![Image](https://github.com/user-attachments/assets/1e0e8276-f27a-4897-ac8e-5e8ab307fdde)

<h3>Step 4: Installing additonal files</h3>

- From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)
- Click Next: Follow the setup instructions.
- From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.
- Click Next: Follow the setup instructions.

![Image](https://github.com/user-attachments/assets/ae12aa51-d996-48f5-a8f9-5dbd841e6eb6)

![Image](https://github.com/user-attachments/assets/df5364f3-94b3-4316-8b4d-f0695842ac34)

<h3>Step 5: MySQL Installation</h3>
 
  - From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
   - Launch Configuration Wizard (after install) 
    - Standard Configuration 
   - Username: root
  - Password: Password1
- Follow the prompt to finish installation

![Image](https://github.com/user-attachments/assets/e42fff20-86cf-4fd7-82e1-b8d98992341f)

<h3>Step 6: Installing PHP in IIS</h3>

- Open IIS as an Admin
- Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)
  
![Image](https://github.com/user-attachments/assets/36980173-f715-4781-914a-eba34e1ab857)

![Image](https://github.com/user-attachments/assets/09f497e5-ab7b-4c73-a056-c1548bc1928c)

![Image](https://github.com/user-attachments/assets/d20d38f1-e6a4-4492-9459-038ef4931678)


</h3>Note that some extensions are not enabled</h3>

- Go back to IIS, sites -> Default -> osTicket
- Double-click PHP Manager
- Click “Enable or disable an extension”Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll

![Image](https://github.com/user-attachments/assets/8569dd86-e7ee-4330-90fe-674bf6ff1911)

</h3>Reload IIS (Open IIS, Stop and Start the server)</h3>


![Image](https://github.com/user-attachments/assets/7d42c7de-5c4e-4afa-947c-e85dc4ebc96e)

</h3>Step7: osTicket Install</h3>

- From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”
- Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”

![Image](https://github.com/user-attachments/assets/9133bdc3-77a1-4f62-8b3c-cc62edf4cfb4)

![Image](https://github.com/user-attachments/assets/099bf52e-8e05-49bc-961a-d671bf9f6efe)

![Image](https://github.com/user-attachments/assets/86a4aec3-9eca-47ae-8b6b-a884b3d5eee4)

</h3>Rename the ost-sampleconfig.php</h3>

- From: ost-sampleconfig.php
- To: ost-config.php

![Image](https://github.com/user-attachments/assets/19f365f7-3d42-4dad-b5dc-d2e4c4274eb4)

![Image](https://github.com/user-attachments/assets/dd28c2a5-952a-4ae8-a970-b621e4809ce9)


</h3>Assign Permissions: ost-config.php</h3>

- Disable inheritance -> Remove All
- To: New Permissions -> Everyone -> All

![Image](https://github.com/user-attachments/assets/7bb7b89a-41f3-428c-ac03-a99c29f2e966)

![Image](https://github.com/user-attachments/assets/04b8667d-a05e-45dc-ad6e-c53d534fb65b)

![Image](https://github.com/user-attachments/assets/150152c2-2ac6-42d3-8ef0-9ceabca55c99)

![Image](https://github.com/user-attachments/assets/1101baf2-aed3-41dd-a433-384264b8454b)

<h3>Step 8: Install HeidiSQL</h3>

- Open Heidi SQL
- Create a new session, root/root
- Connect to the session
- Create a database called “osTicket”

![Image](https://github.com/user-attachments/assets/b477bc99-032a-4d40-9656-b7b69bee324e)

![Image](https://github.com/user-attachments/assets/678ddebd-12a2-45d6-bed3-43c1f16d9d06)

![Image](https://github.com/user-attachments/assets/785afad3-2a90-4783-938d-5bf7bfa093c8)

</h3>Go back to IIS</h3>

- Go to sites -> Default -> osTicket
- On the right, click “Browse *:80”

![Image](https://github.com/user-attachments/assets/026ef34a-f928-42bf-abce-cddb13f14ece)

<h3>Step 9: Setting up osTicket in the browser</h3>
 
 - Name: Helpdesk
  - Email: whichever email you want
  - First Name: your first name
  - Last Name: your last name
  - Email Address: whichever email you want (needs to be different from the Default Email)
  - Username: user_admin 
  - Password: Password1 
  
- MySQL Database: osTicket
- MySQL Username: root
- MySQL Password: root
- Click “Install Now!”
  
![Image](https://github.com/user-attachments/assets/146e3261-f47f-4da0-9696-10e5e51f2b3c)


🎉Congratulations! You have sucessfully installed osTicket!🎉

<p align="center">
<img src="https://i.imgur.com/F52ypHn.png" height="80%" width="80%" alt="Azure Free Account"/>

