# osticket-prereqs
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket. We will be going through the entire installation process together. Part 1 of 3
<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- MySQL 5.5.62
- HeidiSQL

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Remote Desktop Protocol (RDP)
- Microsoft Visual C++ Redistributable Files
- MySQL Server 5.5.62
- PHP 7.3
- HeidiSQL Database Client

<h2>Installation Steps</h2>
<p>
<img width="2304" height="1463" alt="Screenshot (5)" src="https://github.com/user-attachments/assets/10a3534f-8f73-47ce-9763-f0b93dc7fd96" />
<img width="558" height="553" alt="Screenshot 2026-01-20 211839" src="https://github.com/user-attachments/assets/52d2e9c9-58d8-46e5-8f7c-c70c7b9918d3" />
</p>
<p>
Step 1: Hi there! Prepare to install the osTicketing system with me. Start by creating a virtual machine in azure named "osTicket-vm" or similar with a resource group under the name of "osTicket." Be sure to select Windows 10 Pro in image with at least 2 vcpus for the size. At the bottom of this creation page, it should prompt you to create a username and password. For the username, type in "labuser," and for the password, type in "osTicketPassword1!" as this will be your log in info each time you log into your remote desktop. At the very bottom, make sure you check the licensing agreement so it will let you proceed. Then right belolw that, hit next for the "disks" page.
</p>
<p>
 <img width="554" height="263" alt="Screenshot 2026-01-20 211940" src="https://github.com/user-attachments/assets/88e89c19-f086-4502-ba19-1afcbc60a997" />
</p>
<p>
 As there is nothing to do on this page, hit next again for the "networking" page. Within the networking page, switch the subnet to "default" then hit "review+create." Once it's been successfully deployed, hit "create."
</p>
<p>
 <img width="2297" height="1467" alt="Screenshot (6)" src="https://github.com/user-attachments/assets/498e3333-7b57-4014-a7e0-33140cea81b3" />
 <img width="833" height="333" alt="Screenshot 2026-01-20 210006" src="https://github.com/user-attachments/assets/8730c45a-dc30-430f-abae-a9a0c8b17933" />
</p>
<p>
 Step 2: After creating the virtual machine, ensure that the IP address works by logging into your remote desktop using the login info we just created (username: labuser password: osTicketPassword1!)
</p>
<p>
 <img width="418" height="314" alt="Screenshot 2026-01-20 210058" src="https://github.com/user-attachments/assets/5333a250-3160-4cb1-b911-176a13612006" />
</p>
<p>
 You will know you've successfully created the IP adress if this pop up appears after logging in. Hit "yes"
</p>
<p>
<img width="2304" height="1536" alt="Screenshot (1)" src="https://github.com/user-attachments/assets/19f3c295-979a-4671-887e-b41ac6caf0ca" />
Step 3: Once officially logged into your remote desktop, copy the link https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD into the search bar, then download and unzip the osTicket folder.
</p>
<p>
<img width="2304" height="1536" alt="Screenshot (4)" src="https://github.com/user-attachments/assets/cff025db-77e3-49e5-9320-cc2ab54b4579" />
Step 4: Now, we're going to install / Enable IIS in Windows WITH CGI (World Wide Web Services -> Application Development Features -> [X] CGI)
</p>
<p>
<img width="846" height="466" alt="screenshot 4 5" src="https://github.com/user-attachments/assets/ff2a41c6-f1ea-4650-81cc-dbcd609526b1" />
Step 5: From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
</p>
<p>
<img width="855" height="450" alt="screenshot 5 5" src="https://github.com/user-attachments/assets/9892596c-f5ba-4ead-89f4-15ed73a03db9" />
Step 6: Going into the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)
</p>
<p>
<img width="2304" height="1536" alt="Screenshot (5)" src="https://github.com/user-attachments/assets/a318c20f-cd70-426b-bcf0-a79e588f3c08" />
Step 7: Up next, we are going to create the directory C:\PHP. Then from the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder
</p>
<p>

<img width="848" height="455" alt="screenshot 6" src="https://github.com/user-attachments/assets/58d46d6d-7b95-48f4-a40d-5c18ac1b38c1" />
Step 8: From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.
</p>
<p>
<img width="387" height="300" alt="screenshot 7" src="https://github.com/user-attachments/assets/d0a50171-b9d9-488d-8f35-4c4a85e1083f" />
</p>
 <img width="372" height="285" alt="screenshot 8" src="https://github.com/user-attachments/assets/a83c498e-df4c-448d-8563-7811ead40c56" />
 </p>
Step 9: Still in the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi). Typical Setup -> Launch config wizard -> Standard Config -> (username: root/password: root)
</p>
<p>
<img width="843" height="533" alt="screenshot 9" src="https://github.com/user-attachments/assets/588dc7c7-4bcb-4a97-815c-fdc7e3bbbcdb" />
Step 10: After opeining IIS as an admin, register PHP from within (PHP Manager -> C:\PHP\php-cgi.exe)
</p>
<p>
<img width="814" height="699" alt="screenshot 10" src="https://github.com/user-attachments/assets/aadd58a4-f1cf-4193-b16a-8b09eb85e21a" />
Step 11: After reloading IIS (open IIS, stop and start the server), install osTicket v1.15.8. Go into osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot” and rename “upload” to “osTicket”
</p>
<p>
<img width="848" height="529" alt="screenshot 11" src="https://github.com/user-attachments/assets/566c62ff-0a2c-4974-bac4-018ee512ea75" />
Step 12: After reloading IIS again (open IIS, stop and start the server), Go to sites -> Default -> osTicket. Then On the right, click “Browse *:80”
</p>
<p>
<img width="618" height="576" alt="screenshot 12" src="https://github.com/user-attachments/assets/80608b81-b849-4560-9a4d-d34db9d33d84" />
</p>
<p>
 Step 13: Because some extensions are not labled, you will need to go back to IIS, sites -> Default -> osTicket, double-click PHP Manager, click “Enable or disable an extension," enable: php_imap.dll, Enable: php_intl.dll, enable: php_opcache.dll, then observe the changes after refreshing the osTicket site in your browser (screenshot not available due to capture issues during setup).
</p>
<p>
<img width="615" height="568" alt="screenshot 13" src="https://github.com/user-attachments/assets/6b2fcce2-3f09-4693-941e-29ca3a181472" />
</p>
<p>
 OsTicket installation page should look like this afterwards
</p>
<p>
Step 14: Rename: ost-config.php from: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php to: C:\inetpub\wwwroot\osTicket\include\ost-config.php (screenshot not available due to capture issues during setup).
</p>
<p>
<img width="682" height="636" alt="screenshot14" src="https://github.com/user-attachments/assets/46226c9d-5508-40d7-ace4-f0dd0c76de3d" />
</p>
<p>
 Step 15: Assign Permissions: ost-config.php (Disable inheritance -> Remove All New Permissions -> Everyone -> All)
</p>
<p>
<img width="615" height="568" alt="screenshot 13" src="https://github.com/user-attachments/assets/5f002e47-9387-416e-9d9c-1a59dc2d93d3" />
</p>
<p>
<img width="614" height="658" alt="screenshot15" src="https://github.com/user-attachments/assets/c95b55b9-acce-4637-bf5c-e320c6fda86a" />
</p>
<p>
 Step 16: Continue Setting up osTicket in the browser by clicking Continue. Name your help desk and put a default email that customers can send an email to
</p>
<p>
<img width="448" height="339" alt="screenshot16" src="https://github.com/user-attachments/assets/8db38b4d-bf2d-49a4-b58b-1d903e64e2b3" />
</p>
<p>
<img width="699" height="512" alt="screenshot17" src="https://github.com/user-attachments/assets/53487316-705d-4e6d-943a-553be8f7b8e7" />
</p>
<p>
 Step 17: From the “osTicket-Installation-Files” folder, install HeidiSQL. (Open Heidi SQL, create a new session, root/root, connect to the session, then create a database called “osTicket”)
</p>
<p>
Continue Setting up osTicket in the browser (MySQL Database: osTicket, MySQL Username: root, MySQL Password: root, and click “Install Now!” (screenshot no available due to capture issues during setup).
</p>
<p>
<img width="617" height="499" alt="screenshot18" src="https://github.com/user-attachments/assets/71a426c2-ef01-4f6a-a672-17c0b2c10e4b" />
</p>
<p>
 Step 18: Congratulations! You have successfully installed the osTicket system and now can move on to part 2 (post installation)!






















