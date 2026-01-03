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
- MySQL 5.5.62
- HeidiSQL

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Microsoft Visual C++ Redistributable Files
- MySQL Server 5.5.62
- HeidiSQL Database Client
- Item 4
- Item 5

<h2>Installation Steps</h2>
<p>
<img width="2304" height="1463" alt="Screenshot (5)" src="https://github.com/user-attachments/assets/10a3534f-8f73-47ce-9763-f0b93dc7fd96" />
</p>
<p>
Step 1: Start by creating a virtual machine in azure named "osTicket-vm" or similar under a resource group under the name of "osTicket." Be sure to select Windows 10 Pro in image with at least 2 vcpus for the size.  
</p>
<br />
<p>
<img width="2297" height="1467" alt="Screenshot (6)" src="https://github.com/user-attachments/assets/498e3333-7b57-4014-a7e0-33140cea81b3" />
</p>
<p>
Step 2: After creating your virtual machine, open the remote desktop app and connect to that vm's public IP address 
<br />
<p>
 <img width="2304" height="1536" alt="Screenshot (1)" src="https://github.com/user-attachments/assets/19f3c295-979a-4671-887e-b41ac6caf0ca" />
 </p>
<p>
Step 3: Copy https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD into the search bar, then download and unzip the osTicket folder.
</p>
<br />

<img width="2304" height="1536" alt="Screenshot (4)" src="https://github.com/user-attachments/assets/cff025db-77e3-49e5-9320-cc2ab54b4579" />
</p>
Step 4: Install / Enable IIS in Windows WITH CGI (World Wide Web Services -> Application Development Features -> [X] CGI)
</p>
<p>
<img width="846" height="466" alt="screenshot 4 5" src="https://github.com/user-attachments/assets/ff2a41c6-f1ea-4650-81cc-dbcd609526b1" />

Step 5: From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

<img width="855" height="450" alt="screenshot 5 5" src="https://github.com/user-attachments/assets/9892596c-f5ba-4ead-89f4-15ed73a03db9" />
</p>
<p>
Step 6: From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)

<img width="2304" height="1536" alt="Screenshot (5)" src="https://github.com/user-attachments/assets/a318c20f-cd70-426b-bcf0-a79e588f3c08" />
Step 7: Create the directory C:\PHP. Then from the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder



<img width="848" height="455" alt="screenshot 6" src="https://github.com/user-attachments/assets/58d46d6d-7b95-48f4-a40d-5c18ac1b38c1" />
Step 8: From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.


