<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Microsoft Remote Desktop (RDP)
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> 

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- osTicket Installation files
- Heidi SQL

<h2>Installation Steps</h2>

<p>
</p>
<p>
Welcome to my first detailed IT tutorial! To get started, we'll set up a virtual machine (VM) through the Microsoft Azure portal (portal.azure.com). A virtual machine acts as a remote computer, allowing us to work in a controlled environment. Using a VM helps safeguard your physical device from potential issues and gives you a fresh system that can be reused for lab work. Start by creating a resource group named "osTicket." Then, set up a VM with 2 to 4 CPUs; in this tutorial, I'll be using a 4-CPU configuration
  
 <img src="https://i.imgur.com/OPaIGoN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
</p>
<p>Next, go ahead and connect to your new VM using RDP and its public IPv4 address. If you're on a Mac, you'll need to download the Microsoft Remote Desktop app to make the connection.. 
</p>
<img src="https://i.imgur.com/uLVKzxS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
</p>
<p>
Okay, now that you’re connected to your VM, you’ll need to enable IIS. Open the Control Panel and click on “Uninstall a program.” On the left side, choose “Turn Windows features on or off.” A list will show up—just check the box for Internet Information Services to turn it on.
</p>  
<img src="https://i.imgur.com/qtEnuWu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
</p>
<p>
Great! Now that IIS is enabled, the next step is to install the Web Platform Installer. I’ve shared a link here: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6 — it contains everything you’ll need to download and set up osTicket. Just click the link and install the Web Platform Installer from there.
</p>
<img src="https://i.imgur.com/AxHCfQ6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>  
</p>
<p>
After installing the Web Platform Installer, open it up. First, install MySQL 5.5. Next, install the 32-bit (x86) versions of PHP, up to version 7.3. Some items—like the C++ Redistributable, PHP 7.3.8, and PHP Manager for IIS—might not install properly through the app, but you can grab those from the download link I provided earlier.
</p>
<img src="https://i.imgur.com/JJ8bZeJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
</p>
<p>
Next download osTicket. Then extract and copy the "upload" folder into c:\inetpub\wwwroot. Afterwards rename the folder to osTicket
</P>
<img src="https://i.imgur.com/TUGiSKi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
</p>
<p>
Open IIS Manager and restart the server. Once inside IIS manager go to Sites->Default->osTicket on the right, click "Browse*.80" from there your default browser should open osTicket webserver.
</p>
<img src="https://i.imgur.com/4AkTkV0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p>
</p>
<p>
Open IIS Manager.

Go to Sites > Default Web Site > osTicket.

Double-click on PHP Manager.

Click "Disable or enable an extension".

Enable the following extensions:

php_intl.dll

php_opcache.dll

Refresh the osTicket web server.

Confirm that the Intl Extension is now enabled.
</p>
<img src="https://i.imgur.com/APZgUTT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p>
</p>
<p>
Go back into c:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php rename the file to c:\inetpub\wwwroot\osTicket\include\ost-config.php
Assign permissions to ost-config.php Disable inheritance->Removeall
New Permissions->Everyone->all
</p>
<img src="https://i.imgur.com/1nYaYGe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p>
</p>
<p>
Afterwards continue setting up osTicket in the browser (click continue) then you will name the Helpdesk to your liking. Select a default email that will receive emails from customers who submit tickets. 
</p>
<img src="https://i.imgur.com/RmVk3q5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p>
<p>Continue setting up osTicket in your browser:

MySQL Database: osTicket

MySQL Username: root

MySQL Password: Password1

Click “Install Now!”
Once it's installed without errors, congratulations!

Clean up:

Delete the folder: C:\inetpub\wwwroot\osTicket\setup

Set the permissions to "Read" only for: C:\inetpub\wwwroot\osTicket\include\ost-config.php

