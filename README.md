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
Step 1: Hi there! Prepare to install the osTicketing system with me. Start by creating a virtual machine in azure named "osTicket-vm" or similar with a resource group under the name of "osTicket." Be sure to select Windows 10 Pro in image with at least 2 vcpus for the size.  
</p>
<br />
<p>
<img width="2297" height="1467" alt="Screenshot (6)" src="https://github.com/user-attachments/assets/498e3333-7b57-4014-a7e0-33140cea81b3" />
Step 2: After creating your virtual machine, open the remote desktop app and connect to that vm's public IP address 
<br />
<p>
 <img width="2304" height="1536" alt="Screenshot (1)" src="https://github.com/user-attachments/assets/19f3c295-979a-4671-887e-b41ac6caf0ca" />
Step 3: Copy https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD into the search bar, then download and unzip the osTicket folder.
</p>
<br />

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
# post-install-config
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration</h1>
This tutorial outlines the post-install configuration of the open-source help desk ticketing system osTicket. Setting up roles, departments, teams, and agents. Part 2 of 3
<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)
</p>
<p>
<h2>Post-Install Configuration Objectives </h2>
</p>
<p>
1. Establish user and agent roles- Configure agents, teams, and permissions
</p>
<p>
2. Define Ticket Categories and Priorities- Set up help topics, ticket priorities, and SLAs to ensure requests are categorized correctly and handled based on urgency
</p>
<p>
3. Enable email and ticketing and notifications
</p>
<p>
4. Customize intake forms and workflow
</p>
<p>
5. Validate and secure the osTicket system- Test ticket submission, assignment, communication, and resolution workflows, securing the system by finalizing permissions

<h2>Configuration Steps</h2>

<p>
<img width="415" height="412" alt="screenshot19" src="https://github.com/user-attachments/assets/f365203a-dae0-4704-a994-59691c519796" />
</p>
<p>
Step 1: Now that we have the osTicket officially installed, we can go ahead and start getting familiar with the system. Shown above is the login page. We will be using the username: adminuser and password: Password1. Login http://localhost/osTicket/scp/login.php
</p>
<p>
<img width="722" height="323" alt="screenshot 21" src="https://github.com/user-attachments/assets/8d7725d8-1aee-45f2-b01c-f0d0e4ed0387" />
</p>
<p>
<img width="724" height="448" alt="screenshot 22" src="https://github.com/user-attachments/assets/0db72afd-9534-42c0-902e-baf8846c7547" />
</p>
<p>
Step 2: We're going to start off by creating a new role under the name of "Supreme Admin" in the "definition" column.
<p>
<img width="720" height="545" alt="screenshot 23" src="https://github.com/user-attachments/assets/de868e80-b0ac-437f-915f-e1faa69ad1b0" />
</p>
<p>
<img width="720" height="438" alt="screenshot 24" src="https://github.com/user-attachments/assets/71a4ab62-64c7-4b7f-adf5-39e05f67b8cd" />
</p>
<p>
Step 3: Next, we're going assign this role full access before adding it. Be sure to check every box in the "tickets" and "tasks" section under the "permissions" column, then click "add role."
</p>
<p>
<img width="728" height="267" alt="screenshot 25" src="https://github.com/user-attachments/assets/e50eaf54-dc9b-46d5-ba63-1680ccec5e8b" />
</p>
<p>
<img width="725" height="605" alt="screenshot 26" src="https://github.com/user-attachments/assets/2cf244cd-ade9-4ae6-a6c2-d5ffd69be125" />
</p>
<p>
<img width="715" height="613" alt="screenshot 27" src="https://github.com/user-attachments/assets/80cd1b15-b39e-4dae-9f59-3265c9e862fb" />
</p>
<p>
Step 4: Now, we're going to add a new department under the name of "SysAdmins" by going under agents -> Departments -> Add Department. Be sure to set the Parent setting to "Top Level Department." Leaving the rest as is, click "create Department."
</p>
<p>
<img width="738" height="269" alt="screenshot 28" src="https://github.com/user-attachments/assets/20f94a06-011c-4c6b-aa70-5746943a9971" />
</p>
<p>
<img width="723" height="527" alt="screenshot 29" src="https://github.com/user-attachments/assets/0a826ccd-a157-4141-9d2d-5286cc5f0950" />
</p>
<p>
Step 5: We are now going to configure a team under the name "Online Banking." Admin Panel -> Agents -> Teams -> Add New Team. Make sure you click "Create Team" before proceeding.
</p>
<p>
<img width="722" height="529" alt="screenshot 30" src="https://github.com/user-attachments/assets/b910f295-8e07-4243-aeec-fbca428d1ce5" />
</p>
<p>
Step 6: We're going to allow anyone to create tickets by going to Admin Panel -> Settings -> User Settings (UNCHECK: unregistered users can create tickets).
</p>
<p>
<img width="722" height="282" alt="screenshot 31" src="https://github.com/user-attachments/assets/c3a45cab-843c-4199-95b0-c8b096feecf1" />
</p>
<p>
<img width="720" height="639" alt="screenshot 32" src="https://github.com/user-attachments/assets/b4b3092b-b594-4fd5-a38c-0777b6e2a7a0" />
</p>
<p>
<img width="485" height="291" alt="screenshot 33" src="https://github.com/user-attachments/assets/185f3fe0-2c4c-4193-82c8-568105f41f8e" />
</p>
<p>
Step 7: Creating our first agent under the name "Jane Doe," we will be setting her email to Jane@lognpacific.com, username: Jane, and password: Password1. Before moving on, make sure to uncheck both boxes in the password section.
</p>
<p>
<img width="723" height="429" alt="screenshot 34" src="https://github.com/user-attachments/assets/7ade2a9d-4e9e-4956-be73-e185da33bbf9" />
</p>
<p>
Step 8: Still setting up Jane's account, we're going to give her full access to everything by setting her role to "Supreme Admin" and department to "SysAdmin."
</p>
<p>
<img width="718" height="333" alt="screenshot 35" src="https://github.com/user-attachments/assets/2a67bd22-6432-4248-aaa2-42cc8ce6a0e8" />
</p>
<p>
Step 9: Finishing up Jane's account, we're going to set her team under "Online Banking."
</p>
<p>
<img width="717" height="552" alt="screenshot 36" src="https://github.com/user-attachments/assets/dc9009d2-159b-442a-b6b2-03f483c39063" />
</p>
<p>
<img width="487" height="292" alt="screenshot 37" src="https://github.com/user-attachments/assets/c7cb8a34-4979-4105-8c06-d3329cb0742f" />
</p>
<p>
<img width="725" height="428" alt="screenshot 38" src="https://github.com/user-attachments/assets/5705aea5-1aea-4529-869f-088c824cd280" />
</p>
<p>
Step 10: Creating our next agent under the name "John Doe," we will set his email to John@lognpacific.com, username: John, and Password: Password1. Same as Jane's be sure to make sure both boxes are unchecked in the password section. We will also set his department to "support" and his access to "view only."
</p>
<p>
<img width="723" height="320" alt="screenshot 40" src="https://github.com/user-attachments/assets/d81f4723-06d0-465f-af7c-00ead3f70e0c" />
</p>
<p>
After creating your name, Jane, and John, this is what your agents section should look like.
</p>
<p>
<img width="719" height="262" alt="screenshot 41" src="https://github.com/user-attachments/assets/61235f81-3e7e-47c0-a67e-81caa568bb58" />
</p>
<p>
Step 11: Now shifting gears over to the agents panel, we are going to create a couple of users.
</p>
<p>
<img width="483" height="297" alt="screenshot 42" src="https://github.com/user-attachments/assets/ca93ac54-2f36-418c-b91e-ad8250869d3c" />
</p>
<p>
<img width="724" height="308" alt="screenshot 43" src="https://github.com/user-attachments/assets/3fcabeeb-64cd-4c4e-83d2-1933792b41c0" />
</p>
<p>
Step 12: Starting with Karen, we are just going to add her name and email address (Karen@lognpacific.com).
</p>
<p>
<img width="725" height="277" alt="screenshot 57" src="https://github.com/user-attachments/assets/5a0c272f-36c3-4036-96ab-aba1ee1fcf5d" />
</p>
<p>
Step 13: After creating Karen, we are going to create Ken.
</p>
<p>
<img width="485" height="294" alt="screenshot 58" src="https://github.com/user-attachments/assets/40866788-0548-4447-86ca-ed53b0223468" />
</p>
<p>
Step 14: Just like Karen's, we are only going to fill out Ken's name and email address (Ken@lognpacific.com).
</p>
<p>
<img width="720" height="297" alt="screenshot 59" src="https://github.com/user-attachments/assets/e73df5cf-6eb8-457b-9537-0c911b99904c" />
</p>
<p>
After creating them both, this is what your users section should look like. 
</p>
<p>
<img width="732" height="274" alt="screenshot 44" src="https://github.com/user-attachments/assets/6c5ea0de-b579-45a0-86be-458c03c04c10" />
</p>
<p>
Step 15: Shifting back over to the admin panel, we are now going to configure our SLAs. Creating a Sev-A, Sev-B, and Sev-C.
</p>
<p>
<img width="731" height="541" alt="screenshot 45" src="https://github.com/user-attachments/assets/7870592e-8370-439b-b96c-e2548cb0627f" />
</p>
<p>
Step 16: Starting with Sev-A being the most crusial, we are going to set the grace period to 1 hr, and the schedule to 24/7.
</p>
<p>
<img width="729" height="537" alt="screenshot 47" src="https://github.com/user-attachments/assets/cd531da0-3af1-488c-ac99-d77b286964f6" />
</p>
<p>
Step 17: Now creating Sev-B, we are going to give the grace period 4 hrs and the schedule still 24/7.
</p>
<p>
<img width="727" height="538" alt="screenshot 49" src="https://github.com/user-attachments/assets/50e909be-56e3-457f-b46b-2a5d3ee8f30b" />
</p>
<p>
Step 18: And lastly, we're creating Sev-C with a grace period of 8 hrs, and the schedule being Mon-Fri 8am-5pm with U.S Holidays.
</p>
<p>
<img width="730" height="364" alt="screenshot 50" src="https://github.com/user-attachments/assets/4bcc1f4f-c42a-4a38-813c-e85490ca6387" />
</p>
<p>
Your SLA section should consist of all three now.
</p>
<p>
Step 19: The last thing we are going to do for this section is add a few help topics.
</p>
<p>
<img width="734" height="514" alt="screenshot 52" src="https://github.com/user-attachments/assets/4eeb4abf-35c6-4445-9e00-7635c277b727" />
</p>
<p>
Step 20: The first topic will be "Business Critical Outage," making the parent topic "Report a Problem."
</p>
<p>
<img width="744" height="513" alt="screenshot 53" src="https://github.com/user-attachments/assets/952228fd-f613-460c-b022-1f5c312530fa" />
</p>
<p>
Step 21: Our next help topic will be "Personal Computer Issues" under "Report a Problem" as well.
</p>
<p>
<img width="728" height="517" alt="screenshot 54" src="https://github.com/user-attachments/assets/71c51f6a-fa86-4318-8c23-de1c00a27d28" />
</p>
<p>
Step 22: With the last topic being "Equipment Request," under "General Inquiry," this step will close out this section. If you have made it this far, I will see you in the next section :-)
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Ticket Lifecycle: Intake Through Resolution </h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket. Configuring ticket categories and priorities, verifying system functionality through test ticket submissions, and testing the system to ensure tickets were submitted and routed correctly. Part 3 of 3
<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2> Ticket Lifecycle Stages: 
</p>
<p>
Intake-Tickets are submitted into osTicket through the end-user web portal. The system records the request, assigns a ticket number, and places the ticket in an open state for review.
</p>
<p>
Assignment and Communication- Tickets are reviewd and assigned to the appropriate agent or team based on category and priority. Communication with the user is handled through osTicket's intgernal messaging system, ensuring updates are logged within the ticket.
</p>
<p>
Working the Issue- Assigned agents investigate and troubleshoot the issue, document actions taken, and provide updates to the user through the ticket thread until a resolution is identified.
</p>
<p>
Resolution- The issue is resolved by implementing the appropriate fix, confirming functionality with the user, documenting the final solution, and updating the ticket status toresolved or closed.
</p>
<p>
Lifecycle Stages
</p>
<p>
<img width="734" height="307" alt="screenshot 61" src="https://github.com/user-attachments/assets/4afd244b-5b94-419e-9fde-45ccd0427f22" />
</p>
<p>
Step 1: Welcome back! In this section we're going to be creating tickets as end users. But first, start by deleting the "Maintenance" department
</p>
<p>
<img width="639" height="373" alt="screenshot 62" src="https://github.com/user-attachments/assets/04af44d6-f10a-4ecb-8d9a-4e27ed4012ad" />
</p>
<p>
Step 2: And now jumping straight into it, we're going to use the link that takes us to the ticket creating page http://localhost/osTicket and create our very first ticket.
</p>
<p>
<img width="633" height="677" alt="screenshot 63" src="https://github.com/user-attachments/assets/117cf064-74ae-4247-88b4-cba89a5bdd75" />
</p>
<p>
Step 3: Having Karen create the first ticket, fill out her name and email section. In the help desk section, set it to "Report A Problem/Business Critical Outage" because for this scenario, the entire mobile/online bankikng system is down. Be sure to put that in the "Issue Summary" section. For the actual ticket, come up with a breif story that fits the issue like the one pictured above in the example image.
</p>
<p>
<img width="339" height="299" alt="screenshot 65" src="https://github.com/user-attachments/assets/2e94e407-6e9d-49ed-b811-32a435896caf" />
</p>
<p>
<img width="722" height="682" alt="screenshot 66" src="https://github.com/user-attachments/assets/39e1af88-49d5-4cfd-b5a8-5096a74fb17d" />
</p>
<p>
<img width="704" height="562" alt="screenshot 67" src="https://github.com/user-attachments/assets/a74cbd20-4a8f-458d-9c8e-f97a8400b6f4" />
</p>
<p>
Step 4: Log into the osTicket system as John and take a minute to observe that because we set him to "Read Only," he is not allowed to make any changes to the ticket at the moment. So testing this out, insert a note briefly explaining that so we can make sure we see it after logging in as someone else.
</p>
<p>
<img width="728" height="321" alt="screenshot 68" src="https://github.com/user-attachments/assets/d93cde18-438d-4124-ba32-0b3b9815728c" />
</p>
<p>
<img width="724" height="426" alt="screenshot 69" src="https://github.com/user-attachments/assets/8d66dd93-f486-48d4-b9b3-ea6915a606e8" />
</p>
<p>
Step 5: Logging back into the admin panel, we are going to give John full access to the ticket
</p>
<p>
<img width="491" height="193" alt="screenshot 70" src="https://github.com/user-attachments/assets/46c11702-60ec-4afc-bbb8-cb75cc91a93e" />
</p>
<p>
Step 6: Now that John has access to make changes to the ticket, we are first going to set the priority to "emergency." Briefly detail in the section below it
</p>
<p>
<img width="483" height="192" alt="screenshot 71" src="https://github.com/user-attachments/assets/472ae18f-5f45-4c64-b8bd-889d0737723f" />
</p>
<p>
Step 7: Next, set the SLA plan to "Sev-A" to mirror the severity of the scenario
</p>
<p>
<img width="487" height="191" alt="screenshot 72" src="https://github.com/user-attachments/assets/4728ce3d-042c-4f8e-a8ce-5b6b5e802fdb" />
</p>
<p>
Step 8: Molving to the help topic section, set it to "Report A Problem/Business Critical Outage" and insert a brief description of what's going on.
</p>
<p>
<img width="702" height="472" alt="screenshot 73" src="https://github.com/user-attachments/assets/96ac5836-cf07-42d4-a667-a86a263b4000" />
</p>
<p>
Step 9: Have John add a note stating that he will be escalating the ticket to the "SysAdmin" department to triage the ticket
</p>
<p>
<img width="486" height="217" alt="screenshot 74" src="https://github.com/user-attachments/assets/695ec7fa-976e-4331-87e2-bd8fd5878ae2" />
</p>
<p>
Step 10: We will be assigning the ticket to Jane specifically
</p>
<p>
<img width="491" height="208" alt="screenshot 75" src="https://github.com/user-attachments/assets/dca67eff-ac59-4001-962b-d4e6f5a7a155" />
</p>
<p>
Step 11: Set the department to "SysAdmins" and click "transfer."
</p>
<p>
<img width="303" height="227" alt="screenshot 76" src="https://github.com/user-attachments/assets/ef0bf9ba-5cf1-4ed9-a432-db659e748fc5" />
</p>
<p>
Step 12: Log out of the admin panel and log back in as Jane to configure and resolve the ticket.
</p>
<p>
<img width="724" height="273" alt="screenshot 77" src="https://github.com/user-attachments/assets/18c8c5db-c571-4bfe-979c-eebe00ad92f0" />
</p>
<p>
<img width="730" height="566" alt="screenshot 78" src="https://github.com/user-attachments/assets/655543bb-27ef-4f0a-96fc-42b12d37e5fb" />
</p>
<p>
Step 13: Click on the ticket and get updated to the situation by reading over the notes between Karen and John.
</p>
<p>
<img width="719" height="638" alt="screenshot 79" src="https://github.com/user-attachments/assets/25297ac3-1eff-4a33-b8cb-6cde49661f1c" />
</p>
<p>
Step 14: Update the team as Jane in the notes section, letting them know that you are trying to esolve the issue.
</p>
<p>
<img width="711" height="589" alt="screenshot 80" src="https://github.com/user-attachments/assets/726a3dfa-ee53-4ee4-aeba-0677967b45de" />
</p>
<p>
Step 15: Now that the issue is "resolved," add another note letting the team know that they're all set! :-)
</p>
<p>
<img width="710" height="277" alt="screenshot 81" src="https://github.com/user-attachments/assets/f5d8e9f7-d18d-4771-bc84-1a8b264b6284" />
</p>
<p>
Step 16: Change the ticket status to "resolved."
</p>
<p>
<img width="630" height="680" alt="screenshot 82" src="https://github.com/user-attachments/assets/e8f6b8ed-d4ad-4bf2-bd4e-3c3bf51f926d" />
</p>
<p>
Step 17: Going back to the link to create a ticket, we are going to have Ken start this one so fill out his name, email section, and start adding the details of the next ticket. In this scenario, the adobe reader will be down so in the summary, put it under "Report A Problem/Personal Computer Issues." Briefly detail the issue in the neccessary section and remember to click "create ticket."
</p>
<p>
<img width="313" height="235" alt="screenshot 83" src="https://github.com/user-attachments/assets/d84cbe33-8a64-4465-b63b-1c2a426a039c" />
</p>
<p>
Step 18: Log in as John as he will be closing out this ticket.
</p>
<p>
<img width="715" height="586" alt="screenshot 84" src="https://github.com/user-attachments/assets/1aebaff1-0a4e-4133-a652-389e8b091bae" />
</p>
<p>
Step 19: Add in a note stating that you spoke with Ken and he confirmed that adobe is indeed not working. Feel free to use the note in the example pictured above for reference if you are unsure of what to put.
</p>
<p>
<img width="496" height="196" alt="screenshot 85" src="https://github.com/user-attachments/assets/09fef944-4479-483c-9ae3-fa8175fa205b" />
</p>
<p>
Step 20: Set the priority level to "High."
</p>
<p>
<img width="493" height="192" alt="screenshot 86" src="https://github.com/user-attachments/assets/91f3eb06-5119-498c-be8c-c8b80934cdbf" />
</p>
<p>
Step 21: For the SLA level, set it to a 'Sev-B" with a brief note explaining that audit is taking place today.
</p>
<p>
<img width="701" height="397" alt="screenshot 87" src="https://github.com/user-attachments/assets/72f90cf4-fbf9-40a2-b2fd-4aba2e178316" />
</p>
<p>
Step 22: Add a note that you spoke with the desktop admins group to get more info and state what was said (see image above for example).
</p>
<p>
<img width="705" height="317" alt="screenshot 88" src="https://github.com/user-attachments/assets/b5e0828e-47e5-4f34-be0a-c38d1d2b0d5a" />
</p>
<p>
Step 23: Note that the issue was resolved and adobe is back up and running.
</p>
<p>
<img width="709" height="201" alt="screenshot 89" src="https://github.com/user-attachments/assets/a8c1e965-3af1-4d45-ba79-d2415d2172cf" />
</p>
<p>
<img width="490" height="173" alt="screenshot 90" src="https://github.com/user-attachments/assets/f8788cdc-ed23-4978-b2fd-75880925ec79" />

Step 24: Now set the ticket status to "Closed" as this wraps up the project on installing and configuring the osTicketing system! :-)








































