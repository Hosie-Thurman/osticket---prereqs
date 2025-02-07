
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

<h3>Step 3:  Downloading the osTicket Installation files
</h3>

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

</h3>Step7: osTicket Install</h2>

- From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”
- Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”

![Image](https://github.com/user-attachments/assets/9133bdc3-77a1-4f62-8b3c-cc62edf4cfb4)

![Image](https://github.com/user-attachments/assets/099bf52e-8e05-49bc-961a-d671bf9f6efe)

![Image](https://github.com/user-attachments/assets/86a4aec3-9eca-47ae-8b6b-a884b3d5eee4)

</h3>Rename the ost-sampleconfig.php</h2>

- From: ost-sampleconfig.php
- To: ost-config.php

![Image](https://github.com/user-attachments/assets/0d713935-7e69-467a-b6f6-2ec4c4427d50)

![Image](https://github.com/user-attachments/assets/dd28c2a5-952a-4ae8-a970-b621e4809ce9)




<p align="center">
<img src="https://i.imgur.com/zAPFRmU.png" height="70%" width="70%" alt="Azure Free Account"/> <img src="https://i.imgur.com/DUiyQdt.png" height="70%" width="70%" alt="Azure Free Services"/>
</p>


<h3>Step 4: Install osTicket v1.15.8</h3>
     
- Download osTicket (download from within lab files: [link](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6))
- Right click on the file and select extract all
	- Open the new osTicket folder
		- Copy the “upload” folder INTO c:\inetpub\wwwroot
		- Rename “upload” to “osTicket”


<p align="center">
<img src="https://i.imgur.com/BpL8IJE.png" height="80%" width="80%" alt="Azure Free Account"/> <img src="https://i.imgur.com/xSJD7yk.png" height="80%" width="80%" alt="Azure Free Services"/>
</p>
 
     

<h3>Step 5: Reload IIS (Open IIS, Stop and Start the server)
</h3>

- Search for Internet Information Services (IIS) and select open
	- Select restart on right hand side 
- On the left, select Virtualmachine -> Sites -> Default Website -> osTicket
- On the right, click “Browse *:80”
	- This should open osTicket in your web browser
- Before continuing, head back to and open IIS.


<p align="center">
<img src="https://i.imgur.com/OpBkwwj.png" height="80%" width="80%" alt="Azure Free Account"/> <img src="https://i.imgur.com/XNVSNia.png" height="80%" width="80%" alt="Azure Free Services"/>
</p>

<h3>Step 6:Note that some extensions are not enabled</h3>

- Go back to IIS, Sites -> Default Web Site -> osTicket
- Double-click PHP Manager
- Click “Enable or disable an extension” at the bottom under “PHP Extensions”
- Right click and enable the following
    - php_imap.dll (Might be already enabled)
    - php_intl.dll
    - Php_opcache.dll

 
     
![Image](https://github.com/user-attachments/assets/e4782faa-1fe2-4016-8a51-b37f1633d03c)

![Image](https://github.com/user-attachments/assets/fe2f0250-daf6-42a1-842f-8027578721c5)

<h3>Step 7:   Refresh the osTicket site in your browser, observe the changes
</h3>

- Intl Extension should now have a green check mark next to it


<p align="center">
<img src="https://i.imgur.com/ByfN2Fd.png" height="80%" width="80%" alt="Azure Free Account"/>



<h3>Step 8: Rename</h3>
 
- Open Windows Explorer and select C:-> inetpub-> wwwroot-> osTicket-> Include and rename.
	- From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
	- To: C:\inetpub\wwwroot\osTicket\include\ost-config.php


![Image](https://github.com/user-attachments/assets/3740c23d-24f6-4d91-bf06-3763fca20485)

<h3>Step 9: Assign Permissions: ost-config.php</h3>

- Right click ost-config.php, 
- Open Properties -> Security -> Advanced -> Permissions 
- Select Disable inheritance -> Remove all inherited permissions from this object 

![Image](https://github.com/user-attachments/assets/4fb40538-7e34-4f81-98f2-a7f5ba1e2087)

- Afterwards, Select add -> Select a principal  -> type in "everyone" -> check names-> Select OK
	- Allow everyone full control (check all boxes) -> Select apply -> OK

![Image](https://github.com/user-attachments/assets/6fa5ac2e-e6a6-4d12-a30b-d3234bafd257)

![Image](https://github.com/user-attachments/assets/42dba5b5-0909-423b-afa6-26054bc4c4b2)

  
<h3>Step 10: Continue Setting up osTicket in the browser</h3>

- Go back to browser and click continue
  - Name: Helpdesk
  - Email: whichever email you want
  - First Name: your first name
  - Last Name: your last name
  - Email Address: whichever email you want (needs to be different from the Default Email)
  - Username: user_admin 
  - Password: Password1 
  

![Image](https://github.com/user-attachments/assets/777a158b-4260-4dd5-b41c-077494dc4f2a)

<h3>Step 11: Download and Install HeidiSQL</h3>

- Open HeidiSQL -> Select new at the bottom left corner 
   - User: root
   - Password : Password
- Select Open
- On the left side, right click “Unamed” -> “Create New” -> “Database
- Name it “osTicket” and select OK

 <p align="center">
<img src="https://i.imgur.com/mDBWQ5k.png" height="70%" width="70%" alt="Azure Free Account"/> <img src="https://i.imgur.com/ADJYQyB.png" height="70%" width="70%" alt="Azure Free Services"/>
</p>

<h3>Step 12:  Go back to the browser and continue setting up osTicket by filling out the fields.</h3>


- MySQL Database: osTicket (the one you just created in HeidiSQL)
- MySQL Username: root
- MySQL Password: Password1
- Finally, click Install Now

![Image](https://github.com/user-attachments/assets/68c23ddf-320c-4851-85dd-4c42636e8da3)

![Image](https://github.com/user-attachments/assets/71cc9e9f-ae1b-48d5-accd-9113f5833539)


🎉Congratulations! You have sucessfully installed osTicket!🎉

<p align="center">
<img src="https://i.imgur.com/F52ypHn.png" height="80%" width="80%" alt="Azure Free Account"/>

<h3>Tips!</h3>

- To create tickets as a user: http://localhost/osTicket/
- To log in as an Admin or help desk professional: http://localhost/osTicket/scp

<h3>Step 13: Cleanup.</h3>

- Go to C: -> inetpub->wwwroot->osTicket->setup
    - Delete the contents in the setup folder
    - Afterwards, delete the setup folder
- Go to C:-->Inetpub-->wwwroot-->osTicket-->include
    - Right click on ost-config.php 
    - Select securities -> Advanced -> Click on everyone -> edit to change permissions
	- Allow everyone to only have read and execute, then select OK -> Apply -> OK
	
 <p align="center">
<img src="https://i.imgur.com/wucT3UN.png" height="70%" width="70%" alt="Azure Free Account"/> <img src="https://i.imgur.com/cPSx6VL.png" height="70%" width="70%" alt="Azure Free Services"/>
</p>	


Click [here](https://github.com/miquelmanaois/osTicket-post-installing) to move on to part 2 of this tutorial!

