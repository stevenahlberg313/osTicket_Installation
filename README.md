<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This project is a simple guide to the necessary prerequisites and initial installation of osTicket. osTicket is an open source, relatively cost-effective, self-hosted, and reliable support ticketing software used by approximately 15,000 organizations worldwide.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10 Enterprise multi-session, version 22H2 - x64 Gen2

<h2>List of Prerequisites</h2>

- Configure example virtual machine through Microsoft Azure
- Download osTicket https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD
- Install and configure Internet Information Services (IIS)
- Install osTicket
- Configure osTicket to what is needed

<h2>Installation Steps</h2>

<p> To facilitate this example installation, I created and deployed a virtual machine within Microsoft Azure. (Assuming you are working with a physical computer, this step is unnecessary for you if you wish to follow along.)
<img <img width="2334" height="523" alt="Screenshot 2026-08-10 191906" src="https://github.com/user-attachments/assets/6910c8c8-47fd-4b75-9d7e-3cb668c48d7b" />
</p>
<p>
I used remote desktop to login to my VM. (Equivalent of logging into a physical computer.)
</p>
<br />

<p>
<img <img width="400" height="485" alt="Screenshot 2026-08-10 193058" src="https://github.com/user-attachments/assets/74b55030-3b3d-4021-a96d-3fc6b201c53e" />

</p>
<p>
Using the link provided (https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD) , I downloaded and extracted the necessary installation files for osTicket.
</p>
<br />

<p>
<img <img width="1115" height="652" alt="Screenshot 2026-08-10 204221" src="https://github.com/user-attachments/assets/3d7fe302-5f1a-4c04-a256-3c88341ecd90" />


<p>
<img <img width="1142" height="632" alt="Screenshot 2026-08-10 204348" src="https://github.com/user-attachments/assets/710da985-2c76-462b-8d76-660b0cbfbb22" />


</p>
<p>
The extracted files looked like this following image.
</p>
<br />

<p>
<img <img width="1170" height="650" alt="Screenshot 2026-08-10 204515" src="https://github.com/user-attachments/assets/78699f89-ff9c-45fd-b52b-cb032bb3bd91" />


</p>
<p>
Next, I went to "Turn Windows Features on or off" within Control Panel> Programs> Programs and Features
</p>
<br />

<p>
<img <img width="1123" height="634" alt="Screenshot 2026-08-10 201108" src="https://github.com/user-attachments/assets/90f9ea7a-f97d-42af-8031-0d1299b4e52d" />

</p>
<p>
Upon clicking "Turn Windows Features on or off", I was allowed to search for and activate Internet Information Services (IIS)
</p>
<br />

<p>
<img <img width="1145" height="633" alt="Screenshot 2026-08-10 201653" src="https://github.com/user-attachments/assets/439ef3ef-1d11-46d9-8e8e-be335ca5ad29" />

</p>
<p>
osTicket also required CGI. To find it I expanded Internet Information Services, World Wide Web Services, and Application Development Features.
</p>
<br />

<p>
<img <img width="1124" height="633" alt="Screenshot 2026-08-10 202410" src="https://github.com/user-attachments/assets/5ef04041-1b08-43fb-adfc-5bd2e4e57933" />

</p>
<p>
Upon selecting "OK", CGI began downloading.
</p>
<br />

<p>
<img <img width="1120" height="629" alt="Screenshot 2026-08-10 202841" src="https://github.com/user-attachments/assets/fe34acc8-d433-467c-b4fe-adeee23c5349" />

</p>
<p>
I needed to install PHPManagerForIIS_V1.5.0. To do so, I navigated back to the "osTicket Installation Files" folder in File Explorer.
</p>
<br />

<p>
<img <img width="1122" height="636" alt="image" src="https://github.com/user-attachments/assets/56588ea6-af2d-49b2-84c8-24656bcf62b4" />


</p>
<p>
Double clicking PHPManagerForIIS_V1.5.0 began the installation.
</p>
<br />

<p>
<img <img width="1123" height="632" alt="Screenshot 2026-08-10 205455" src="https://github.com/user-attachments/assets/443f5b01-76fc-41af-a5ab-eccea5746c26" />

</p>
<p>
Time came to install the Rewrite Module. Double clicking "rewrite_amd64_en-US" from within the "osTicket Installation Files" folder began that install.
</p>
<br />

<p>
<img <img width="1126" height="629" alt="Screenshot 2026-08-10 210611" src="https://github.com/user-attachments/assets/bc3e33c7-f6e4-4761-b725-9f00a91f680c" />


</p>
<p>
Next, I needed to create a new directory called PHP. Thus, I opened a new File Explorer Window and navigated to the "C" drive within "This PC"
</p>
<br />

<p>
<img <img width="1125" height="629" alt="Screenshot 2026-08-10 214217" src="https://github.com/user-attachments/assets/f0140191-dda6-4032-93c4-06c532c8e8a4" />


</p>
<p>
From the “osTicket Installation Files” folder, I needed to unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder.
</p>
<br />

<p>
<img <img width="1397" height="631" alt="Screenshot 2026-08-10 215116" src="https://github.com/user-attachments/assets/2c5ed8bd-0954-415f-b1d0-80c9042759ad" />


</p>
<p>
The installation of VC_redist.x86.exe from the "osTicket Installation Files" folder came next. A simple double click began the process.
</p>
<br />

<p>
<img <img width="1123" height="631" alt="Screenshot 2026-08-10 220133" src="https://github.com/user-attachments/assets/90806ce8-b442-4405-bb50-174ef6bcb2ab" />

</p>
<p>
From the “osTicket-Installation-Files” folder, I installed MySQL 5.5.62 (mysql-5.5.62-win32.msi). Again, a simple double click began the process.
</p>
<br />

<p>
<img <img width="1208" height="631" alt="Screenshot 2026-08-10 220813" src="https://github.com/user-attachments/assets/acb6e11e-11db-4a9a-8944-0ea70f80d239" />


</p>
<p>
Subsequently, within the setup wizard, I chose the "Standard" configuration for this demonstration.
</p>
<br />

<p>
<img <img width="1122" height="630" alt="Screenshot 2026-08-10 221354" src="https://github.com/user-attachments/assets/a05ba699-0604-42a8-bdc2-6a0303ed762b" />


</p>
<p>
Then set it to install as a Windows Service.
</p>
<br />

<p>
<img <img width="1117" height="636" alt="Screenshot 2026-08-10 221617" src="https://github.com/user-attachments/assets/8090e475-f08a-4a18-9568-d40908c784d2" />


</p>
<p>
Then I needed to configure the MySQL Server security with a password
</p>
<br />

<p>
<img <img width="1121" height="636" alt="Screenshot 2026-08-10 222006" src="https://github.com/user-attachments/assets/f6af7b7b-5d9a-4e7b-9f83-adcd2ad02a88" />


</p>
<p>
Finally, the configuration wizard allowed me to execute the installation.
</p>
<br />

<p>
<img <img width="1123" height="632" alt="Screenshot 2026-08-10 222428" src="https://github.com/user-attachments/assets/1b151111-94b8-48d2-8544-c0d474502bc9" />

</p>
<p>
I then needed to open IIS as the Admin. To accomplish this I navigated to the search bar in the bottom left and searched for "ISS". When it appeared, I made sure to select "Run as Administrator". 
</p>
<br />

<p>
<img <img width="831" height="677" alt="Screenshot 2026-08-10 223159" src="https://github.com/user-attachments/assets/fa88902b-0c35-4b00-9c23-45555ee0c935" />


</p>
<p>
From inside the ISS window, I had to register PHP. To accomplish this, I had to open the PHP manager, then select "Register new PHP version".
</p>
<br />

<p>
<img <img width="1642" height="265" alt="Screenshot 2026-08-10 224430" src="https://github.com/user-attachments/assets/35798b66-8435-47ff-95c1-d206c59763da" />

<p>
<img <img width="919" height="673" alt="Screenshot 2026-08-10 224535" src="https://github.com/user-attachments/assets/5b4c5d87-f915-4175-a603-3c2ce0d2a603" />


</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

