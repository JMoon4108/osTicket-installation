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

- Windows 10</b> (22H2)

<h2>List of Prerequisites</h2>

- Microsoft URL Rewrite Module for IIS (version 2.0, x64)
- Microsoft Visual C++ Redistributable (x86)
- MySQL for Windows (version 5.5.62, x86)
- PHP for Windows (version 7.3.8, x86)
- PHP Manager for IIS (version 1.5.0, x64)

<h2>Installation Steps</h2>

<p>
<img src="https://imgur.com/giqBLsG.png" alt="Prerequisite files install"/>
</p>
<p>
Install prereq_files.zip raw files from GitHub on to your desktop for easy access.
</p>
<br />

<p>
<img src="https://imgur.com/Le1nC05.png" height="80%" width="80%" alt="Unzip prerequisite files"/>
</p>
<p>
Unzip prereq_files.zip to desktop.
</p>
<br />

<p>
<img src="https://imgur.com/MC1vaip.png" height="80%" width="80%" alt="Enable IIS with CGI"/>
</p>
<p>
Open start menu and navigate to Control Panel. From control panel click "uninstall a program" and open "Turn Windows features on or off" scroll till you find Internet Information Services. Tick the box and then enable CGI. Internet Information Services -> World Wide Web Services -> Application Development Features -> CGI. Once both are enabled press OK.
</p>
<br />

<p>
<img src="https://imgur.com/ShxcZ4t.png" height="80%" width="80%" alt="PHP Manager"/>
</p>
<p>
Double click and install "PHPManagerForIIS_V1.5.0.msi" from prereq_files folder on desktop. Agree to any dialog and click next until install finishes.
</p>
<br />

<p>
<img src="https://imgur.com/lmKLvtU.png" height="80%" width="80%" alt="IIS URL Rewwrite"/>
</p>
<p>
Install "rewrite_amd64_en-US.msi" in the same way as PHP Manager in previous step.
</p>
<br />

<p>
<img src="https://imgur.com/Fz9XFpD.png" height="80%" width="80%" alt="Create PHP"/>
</p>
<p>
Navigate to your C:\ directory using file explorer and create a new folder named "PHP".
</p>
<br />

<p>
<img src="https://imgur.com/MBpjgEY.png" height="80%" width="80%" alt="PHP extract"/>
</p>
<p>
In prereq_files folder right click "php-7.3.8-nts-Win32-VC15-x86.zip" and choose extract all. Use the browse button to navigate to the PHP folder on the C:\ directory and click choose folder. Files should be contained directly in the PHP folder, if a folder is created within PHP with the files inside that one, you will need to move them to PHP.
</p>
<br />

<p>
<img src="https://imgur.com/JzZkwSh.png" height="80%" width="80%" alt="VC redist install"/>
</p>
<p>
Next from prereq_files install "VC_redist.x86.exe". Agree to the terms and press install once launched.
</p>
<br />

<p>
<img src="https://imgur.com/CgacgQ3.png" height="80%" width="80%" alt="MySQL install"/>
</p>
<p>
Install "mysql-5.5.62-win32.msi" and leave box ticked to launch MySQL configuration wizard.
</p>
<br />

<p>
<img src="https://imgur.com/FYIw4Cr.png" height="80%" width="80%" alt="MySQL standard config"/>
</p>
<p>
Click next until you have to choose configuration type, select Standard Configuration.
</p>
<br />

<p>
<img src="https://imgur.com/sw4I7Uq.png" height="80%" width="80%" alt="MySQL password"/>
</p>
<p>
For demonstration set password to "root" although another password can be chosen, be sure to write it down for later use.
</p>
<br />

<p>
<img src="https://imgur.com/Cj9Afxj.png" height="80%" width="80%" alt="IIS as admin"/>
</p>
<p>
Using the start menu search "IIS" and launch the Internet Information Services (IIS) Manager as an administrator.
</p>
<br />

<p>
<img src="https://imgur.com/B1ohOtl.png" height="80%" width="80%" alt="PHP Manager settings"/>
</p>
<p>
From the IIS home screen open PHP Manager.
</p>
<br />

</p>
<p>
<img src="https://imgur.com/fSlN6a3.png" height="80%" width="80%" alt="Register PHP"/>
</p>
<p>
From this menu open "Register new PHP version", using the ellipsis (3 dots) browse through the PHP file on your C drive and select "php-cgi.exe" and press ok to return to IIS.
</p>
<br />

<p>
<img src="https://imgur.com/gZjlCqg.png" height="80%" width="80%" alt="Restart sever"/>
</p>
<p>
Right click the main directory (name of your computer) and stop the server, right click again and start it to refresh the new PHP settings. You can also go back to the main directory and click restart on the right side.
</p>
<br />

<p>
<img src="https://imgur.com/mxHwBHj.png" height="80%" width="80%" alt="Extract and copy"/>
</p>
<p>
Returning the the installation files, unzip "osTicket-v1.15.8.zip" and copy the “upload” folder into “c:\inetpub\wwwroot”. Rename the copied "upload" folder to "osTicket" (Make sure to keep lower case and capitals exactly as shown).
</p>
<br />

<p>
<img src="https://imgur.com/H0Ivo3u.png" height="80%" width="80%" alt="Restart server 2"/>
</p>
<p>
Reload IIS (Open IIS, Stop and Start the server)
</p>
<br />

<p>
<img src="https://imgur.com/zPLp0VU.png" height="80%" width="80%" alt="Browse HTTP"/>
</p>
<p>
In IIS, Go to sites -> Default Web Site -> osTicket, and click "Browse *:80" on the right side. This will show you the remaining requirements to run osTicket.
</p>
<br />

<p>
<img src="https://imgur.com/dvSafWs.png" height="80%" width="80%" alt="PHP enable extensions"/>
</p>
<p>
Inside the PHP Manager for osTicket, open the "Enable or disable extension" menu.
</p>
<br />

<p>
<img src="https://imgur.com/PSynfnr.png" height="80%" width="80%" alt="PHP extensions"/>
</p>
<p>
Enable the 3 following extensions: "php_imap.dll", " php_intl.dll", and "php_opcache.dll".
</p>
<br />

<p>
<img src="https://imgur.com/vvWohPr.png" height="80%" width="80%" alt="Confirm extensions"/>
</p>
<p>
Refresh the webpage for osTicket installer and the following prerequsites will have updated.
</p>
<br />

<p>
<img src="https://imgur.com/mXni8Qg.png" height="80%" width="80%" alt="Config file"/>
</p>
<p>
In file explorer, navigate to "C:\inetpub\wwwroot\osTicket\include\" and rename the file "ost-sampleconfig.php" to "ost-config.php".
</p>
<br />

<p>
<img src="https://imgur.com/tyEcS4q.png" height="80%" width="80%" alt="Config Permissions"/>
</p>
<p>
Right click the newly renamed "ost-config.php" and select properties. Security -> Advanced, and disable inheritance. This will remove all permissions currently assigned.
</p>
<br />

<p>
<img src="https://imgur.com/WD5ZQx6.png" height="80%" width="80%" alt="Set permissions"/>
</p>
<p>
Still within Security -> Advanced, click "Add". This dialog will pop-up, click "Select a principal". Enter "everyone" into the "Enter the object name to select" box and click check names to verify. Press OK and make sure "Full control" is selected.
</p>
<br />

<p>
<img src="https://imgur.com/GfjUWD2.png" height="80%" width="80%" alt="Apply permissions"/>
</p>
<p>
Make Sure to Select "Apply" so permissions are set.
</p>
<br />

<p>
<img src="https://imgur.com/h9MBVmT.png" height="80%" width="80%" alt="HeidiSQL install"/>
</p>
<p>
Returning to the prereq_files folder, install "HeidiSQL_12.3.0.6589_Setup.exe", this is to setup a database for osTicket to store its data.
</p>
<br />

<p>
<img src="https://imgur.com/iYg5tbC.png" height="80%" width="80%" alt="SQL session"/>
</p>
<p>
Create a new session within HeidiSQL make the password the same as the MySQL password, in this case "root".
</p>
<br />

<p>
<img src="https://imgur.com/blz4phU.png" height="80%" width="80%" alt="New database"/>
</p>
<p>
Within your session right click the top directory and select create new -> Database.
</p>
<br />

<p>
<img src="https://imgur.com/a7axki6.png" height="80%" width="80%" alt="Database name"/>
</p>
<p>
In the pop-up dialog, set the name to "osTicket" (case sensitive) and press "OK".
</p>
<br />

<p>
<img src="https://imgur.com/GBprmKS.png" height="80%" width="80%" alt=""/>
</p>
<p>
Return to your HTTP (Browse *:80) window for the osTicket installer and select continue. Copy information as shown or create your own information. The Admin user information will be how you login and configure osTicket so be sure to write it down. For the database make sure the "MySQL Database" is "osTicket" and the password and username are consistent with your HeidiSQL session. After all the information is filled out, press "Install Now".
</p>
<br />

<p>
<img src="https://imgur.com/RTkHqDB.png" height="80%" width="80%" alt="Verification"/>
</p>
<p>
To verify installation was successful, open a new window and go to "localhost/osTicket/scp/login.php". This is how to access the osTicket configuration for the next tutorial repositories.
</p>
<br />
