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

<p> To facilitate this example installation, I created and deployed a virtual machine within Microsoft Azure. (Assuming you are working with a physical computer, this step is unnecessary if you wish to follow along.)
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
Upon clicking "Turn Windows Features on or off", I was allowed to search for and activate Internet Information Services (IIS). osTicket requires IIS to act as the web server that will host and deliver osTicket to the users' browser.
</p>
<br />

<p>
<img <img width="1145" height="633" alt="Screenshot 2026-08-10 201653" src="https://github.com/user-attachments/assets/439ef3ef-1d11-46d9-8e8e-be335ca5ad29" />

</p>
<p>
osTicket also required CGI. To find it I expanded Internet Information Services, World Wide Web Services, and Application Development Features. CGI is necessary because it allows IIS to execute PHP scripts and process the data that makes the osTicket application function.
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
I needed to install PHPManagerForIIS_V1.5.0. To do so, I navigated back to the "osTicket Installation Files" folder in File Explorer. PHPManagerForIIS configures and manages the PHP file on IIS to enable osTicket's PHP file to run correctly.
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
Time came to install the Rewrite Module. Double clicking "rewrite_amd64_en-US" from within the "osTicket Installation Files" folder began that install. The Rewrite Module facilitates osTicket's ability to use clean, user-friendly URLs by converting web addresses to the correct osTicket pages.
</p>
<br />

<p>
<img <img width="1126" height="629" alt="Screenshot 2026-08-10 210611" src="https://github.com/user-attachments/assets/bc3e33c7-f6e4-4761-b725-9f00a91f680c" />


</p>
<p>
Next, I needed to create a new directory called PHP. Thus, I opened a new File Explorer Window and navigated to the "C" drive within "This PC". This action created the dedicated hub for PHP files and configuration necessary for osTicket to run through IIS.
</p>
<br />

<p>
<img <img width="1125" height="629" alt="Screenshot 2026-08-10 214217" src="https://github.com/user-attachments/assets/f0140191-dda6-4032-93c4-06c532c8e8a4" />


</p>
<p>
From the “osTicket Installation Files” folder, I needed to unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder. Doing this allowed Windows and osTicket the ability to find and use the needed PHP files to operate the application.
</p>
<br />

<p>
<img <img width="1397" height="631" alt="Screenshot 2026-08-10 215116" src="https://github.com/user-attachments/assets/2c5ed8bd-0954-415f-b1d0-80c9042759ad" />


</p>
<p>
The installation of VC_redist.x86.exe from the "osTicket Installation Files" folder came next. osTicket needed VC_redist.x86.exe because PHP depends on Visual C++ runtime libraries to run properly on Windows. A simple double click began the process.
</p>
<br />

<p>
<img <img width="1123" height="631" alt="Screenshot 2026-08-10 220133" src="https://github.com/user-attachments/assets/90806ce8-b442-4405-bb50-174ef6bcb2ab" />

</p>
<p>
From the “osTicket-Installation-Files” folder, I installed MySQL 5.5.62 (mysql-5.5.62-win32.msi). This created the database system that osTicket relies upon to store and manage ticket and user information. Again, a simple double click began the process.
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
I then needed to open IIS as the Admin. To accomplish this, I navigated to the search bar in the bottom left and searched for "ISS". When it appeared, I made sure to select "Run as Administrator". 
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
I made sure to select the "php-cgi" file from within the PHP folder I created on the C drive.
</p>
<br />

<p>
<img <img width="1296" height="733" alt="Screenshot 2026-08-10 225543" src="https://github.com/user-attachments/assets/7c680cfa-a4b9-44bd-abf5-8b8e8781dfa8" />


</p>
<p>
To ensure the server functions properly, I used the restart button in the top right of the IIS window.
</p>
<br />

<p>
<img <img width="197" height="353" alt="Screenshot 2026-08-10 230017" src="https://github.com/user-attachments/assets/fb4d041a-8e74-4e6e-aeb7-efcc7c06bc3a" />


</p>
<p>
After all of that, it had finally come time to actually "install" osTicket. To fulfill this, I reopened the “osTicket-Installation-Files” folder, unzipped "osTicket-v1.15.8.zip", and copied the "upload" folder into "c:inetpub\wwwroot". This allowed IIS to access and serve osTicket's file through the web browser.
</p>
<br />

<p>
<img <img width="1488" height="792" alt="Screenshot 2026-08-10 231146" src="https://github.com/user-attachments/assets/50fe6f78-f710-4b3e-8ad3-06189494917a" />

<p>
<img <img width="1133" height="622" alt="Screenshot 2026-08-10 231340" src="https://github.com/user-attachments/assets/0869ed1a-c175-4b98-92dc-4265b9687b8c" />

</p>

</p>
<p>
Then the upload folder I just copied into "c:inetpub\wwwroot" needed to be renamed "osTicket".
</p>
<br />

<p>
<img <img width="1119" height="202" alt="Screenshot 2026-08-10 231822" src="https://github.com/user-attachments/assets/d3bc9dbf-ca0a-4c92-b957-3e996143f565" />


</p>
<p>
To force the server's information to update, I restarted it again with the button up in the top right of the IIS window.
</p>
<br />

<p>
<img <img width="197" height="353" alt="Screenshot 2026-08-10 230017" src="https://github.com/user-attachments/assets/8e260afd-ce77-47a3-ac29-70d67e8b44ce" />


</p>
<p>
In order to check that the IIS is functioning properly, in the IIS window, I navigated through "Admin-1> Sites> Default Web Site> osTicket. Then on the far right of the screen I clicked "Browse*:80(http)".
</p>
<br />

<p>
<img <img width="427" height="257" alt="Screenshot 2026-08-10 232742" src="https://github.com/user-attachments/assets/4813eda3-56ee-43c5-a113-c70d13e46e7c" />

<p>
<img <img width="201" height="245" alt="Screenshot 2026-08-10 233147" src="https://github.com/user-attachments/assets/d934bfe0-a05e-42df-afd2-7be579972cc5" />


</p>
<p>
As I made no mistakes, I was greeted with this screen.
</p>
<br />

<p>
<img <img width="1612" height="806" alt="Screenshot 2026-08-10 233433" src="https://github.com/user-attachments/assets/7632c4c4-45f5-41eb-bd0b-6c86b001777a" />

</p>
<p>
The next step was to enable some of the extensions that might be useful later on. Specifically, "php_imap.dll", php_intl.dll, and php_opcache.dll. To achieve this, I went back to the IIS window, navigated to Sites> Default Web Site> osTicket, and double clicked the PHP Manager.
</p>
<br />

<p>
<img <img width="745" height="619" alt="Screenshot 2026-08-10 234505" src="https://github.com/user-attachments/assets/5df37a8c-67ba-4d55-9f7f-a0ec9c2940d0" />


</p>
<p>
From there I clicked "Enable or disable an extension", and enabled the three extensions I wanted.
</p>
<br />

<p>
<img <img width="356" height="156" alt="Screenshot 2026-08-10 234741" src="https://github.com/user-attachments/assets/f8fe37e0-314b-4d16-976d-3915dd01c758" />

<p>
<img <img width="435" height="404" alt="Screenshot 2026-08-10 235002" src="https://github.com/user-attachments/assets/cde93957-8079-429d-80e8-f0788a47e572" />


</p>
<p>
Once again to force the server's information, I restarted the IIS.
</p>
<br />

<p>
<img <img width="197" height="353" alt="Screenshot 2026-08-10 230017" src="https://github.com/user-attachments/assets/50c8e65e-7e9c-451e-92bc-1d9267466c87" />


</p>
<p>
To ensure the extensions have been enabled, I went back the the web page for an update.
</p>
<br />

<p>
<img <img width="1689" height="807" alt="Screenshot 2026-08-10 235527" src="https://github.com/user-attachments/assets/bfd27486-7e09-4c01-911d-3e65db2f6dfe" />


</p>
<p>
To facilitate configuration, I renamed "C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php" to "C:\inetpub\wwwroot\osTicket\include\ost-config.php"
</p>
<br />

<p>
<img <img width="593" height="67" alt="Screenshot 2026-08-11 000215" src="https://github.com/user-attachments/assets/f9c602cf-e275-4826-a915-ffa4f321220a" />

<p>
<img <img width="592" height="61" alt="Screenshot 2026-08-11 000258" src="https://github.com/user-attachments/assets/cf338faf-d2f5-4d6c-b161-9f7f86187664" />


</p>
<p>
The following step was to assign permissions within "ost-config.php" to allow osTicket to make changes to that file. To complete it, I right clicked "ost-config.php", selected properties, then security, then advanced, and disable inheritance.
</p>
<br />

<p>
<img <img width="1788" height="545" alt="Screenshot 2026-08-11 001358" src="https://github.com/user-attachments/assets/80e380f7-8092-4199-a6ac-91f07d56476d" />


</p>
<p>
For the sake of this demonstration, I will select "add", "select principal", and give "everyone" full control of this file. Not a good thing to do in an actual real world setting, but for the sake of simplicity this is how it will be configured.
</p>
<br />

<p>
<img <img width="915" height="595" alt="Screenshot 2026-08-11 002111" src="https://github.com/user-attachments/assets/3b3757b2-84e6-4a91-9d2a-9a2044e03fe2" />




</p>
<p>
Then it was time to actually configure the osTicket basic installation. To accomplish this, I went back to the osTicket webpage, clicked "continue" and filled out the installation page.
</p>
<br />

<p>
<img <img width="821" height="1220" alt="Screenshot 2026-08-11 002750" src="https://github.com/user-attachments/assets/10379988-4dab-4545-b17f-9a7c0e8cdf27" />


</p>
<p>
But before I could click "Install Now", I needed to install "HeidiSQL". To do so, I opened, the "osTicket-Installation-Files" folder and opened "HeidiSQL".
</p>
<br />

<p>
<img <img width="1357" height="516" alt="Screenshot 2026-08-11 004115" src="https://github.com/user-attachments/assets/b6686077-d897-42bf-8d0a-65f1714a02c1" />


</p>
<p>
Once inside HeidiSQL, I needed to make a connection to my database in osTicket. To accomplish that, I started by navigating to the "New" button in the bottom left of the window.
</p>
<br />

<p>
<img <img width="687" height="477" alt="Screenshot 2026-08-11 004507" src="https://github.com/user-attachments/assets/18f2c52b-15ce-40a7-8248-a91e95b82fd8" />



</p>
<p>
Then configured the user and password to match what I used before, and clicking open to move on to the next step.
</p>
<br />

<p>
<img <img width="685" height="480" alt="Screenshot 2026-08-11 004853" src="https://github.com/user-attachments/assets/9bb7d8cc-297a-472e-9346-7517b4e18cd3" />



</p>
<p>
The next step was to create a new database called osTicket. I right clicked on the "Unnamed" folder, selected "create new", and "Database".
</p>
<br />

<p>
<img <img width="934" height="592" alt="Screenshot 2026-08-11 005501" src="https://github.com/user-attachments/assets/7ab57fab-90f0-44e4-ad2a-336fb29a4e87" />

<p>
<img <img width="928" height="595" alt="Screenshot 2026-08-11 005622" src="https://github.com/user-attachments/assets/fd0fafb9-6a07-4b42-938c-6f39ac0ca4c7" />


</p>
<p>
With that done, I was able to return to the osTicket Basic Installation web page to finish the configuration, and click "Install Now".
</p>
<br />

<p>
<img <img width="822" height="1222" alt="Screenshot 2026-08-11 010106" src="https://github.com/user-attachments/assets/76c82842-7645-489d-8674-aa58db51ef67" />

<p>
<img <img width="820" height="635" alt="Screenshot 2026-08-11 010254" src="https://github.com/user-attachments/assets/6f4c6a63-e454-4c82-bbe7-029c92a49c93" />




</p>
<p>
The final test if this demonstration, was to attempt to log into osTicket as both the Admin and user.
</p>
<br />

<p>
<img <img width="1688" height="412" alt="Screenshot 2026-08-11 011115" src="https://github.com/user-attachments/assets/92a19ab4-2c27-43a0-8134-7d37d63379b3" />

<p>
<img <img width="1685" height="580" alt="Screenshot 2026-08-11 011234" src="https://github.com/user-attachments/assets/cebdb7db-9cda-420d-b2c8-1580a3047d03" />

</p>
