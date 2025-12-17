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

- Azure Virtual Machine
- Heidi SQL
- osTicket Installation files
  


<h2>Installation Steps</h2>

<p>
<img width="926" height="1143" alt="1" src="https://github.com/user-attachments/assets/d8da117f-1d10-4e95-bd40-c3582172694c" />
</p>
<p>
To get started, we will first create a virtual machine. This virtual machine will be housed under a new Resource Group named "osTicket" and the virtual machine (VM) will be named "osticket-vm". When creating the VM, we will be selecting a Windows 10 image, the size of the virtual machine will contain at least 2 vcpus. Set username and password to your preference.
</p>
<br />

<p>
<img width="2740" height="6000" alt="2" src="https://github.com/user-attachments/assets/29faee31-2dd0-45cf-b1b6-0a534a67f93c" />

</p>
<p>
Once the VM has been created, we will copy the public IP address of the VM and paste it onto the Remote Desktop application. In the Remote Desktop app, select "show more options" and enter in the username that was created in the first step.
</p>
<br />

<p>
<img width="1174" height="815" alt="3" src="https://github.com/user-attachments/assets/9305bcdf-be6b-4f3a-8d1b-9786b8c4ba2c" />
</p>
<p>
Once logged onto the virtual machine, we will open and download the following files onto our VM. After we download the files, we will extract them to our desktop for ease of accessibility -- <a href="https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0/">OsTicket Installation Files. 
</p>
<br />


<p>
<img width="561" height="420" alt="5" src="https://github.com/user-attachments/assets/fcd11295-7cb6-4712-a523-2bd80923fc5e" />
</p>

<p>
Next, we will have to enable IIS (Internet Information Services) in Windows with CGI. To do this, open up control panel from the start menu -> click "Uninstall a Program" 
</p>
<br />


<p>
<img width="810" height="786" alt="4" src="https://github.com/user-attachments/assets/6504c3c2-3b7d-4184-bebe-69952273b7b6" />
</p>


<p>
Next we will click "Turn Windows features on or off" -> check the box next to the "Internet Information Services" feature. Additionally, we would expand the drop down under "World Wide Web Services" and "Application Development Features" to enable the "CGI" feature on our VM. (If you'd like to perform a safety check to see if IIS has been enabled, type the following loopback address "127.0.0.1" in your search browser and you should see the IIS landing page!)
</p>
<br />


<p>
<img width="474" height="384" alt="6" src="https://github.com/user-attachments/assets/5a1dcc46-6a8a-479c-ba1c-65e5a3eb76e6" />

</p>


<p>
After enabling IIS, we are now ready to proceed with the installation files that had been extracted onto our VM's desktop. Next, we will install PHP manager, found in the Os-Ticket-Installation-Files folder. Follow the installation prompts in order to proceed with the OsTicket application setup.
</p>
<br />


<p>
<img width="709" height="548" alt="7" src="https://github.com/user-attachments/assets/b7150c7c-d22d-4222-9155-5aa02adf08f1" />
</p>

<p>
Once the PHP Manager has been installed, we will install the Rewrite Module next. Follow the prompts until the module has been fully installed.
</p>
<br />


<p>
<img width="694" height="396" alt="8" src="https://github.com/user-attachments/assets/750b4862-c759-463a-a62d-2cf8634bf32f" />

</p>


<p>
The next step involves extracting the relative PHP files from the OsTicket-Installation-Files folder, and placing them in a new folder within the VM's (C:) drive, named "PHP". First, we will create our PHP folder in the drive. Navigate using the following steps in File Explorer and create a folder named "PHP". Click on "This PC" -> "Windows (C:)" -> Create a new folder named "PHP".
</p>
<br />


<p>
<img width="1160" height="807" alt="9" src="https://github.com/user-attachments/assets/3d3497d4-7a19-4d53-9c3e-cee9eb307f49" />
</p>


<p>
Now we will extract the php zip folder "php-7.3.8-nts-Win32-VC15-x86.zip" in the OsTicket-Installation-Files folder onto our newly created PHP folder in the (C:) drive PHP folder. Right-click the php zip folder -> Click Extract All -> Click Browse and extract the zip files into the C:\PHP folder.
</p>
<br />

<p>
<img width="480" height="292" alt="10" src="https://github.com/user-attachments/assets/074905b2-e4a2-483a-bf30-63d2dc99d07a" />
</p>


<p>
Next, we will install the VC_redist.x86 application found in the OsTicket-Installation-Files folder, this is a Microsoft Visual Studio C++ Redistributable necessary for our OsTicket installation.
</p>
<br />


<p>
<img width="491" height="385" alt="11" src="https://github.com/user-attachments/assets/d07419dd-0a35-4df6-be23-756c8c4dd666" />
/>
</p>


<p>
Now we can install the MySQL Server (mysql-5.5.62-win32) from the OsTicket-Installation-Files folder, this will serve as a database for our OsTicket application. Please follow the installation prompts and select "Standard Configuration" when prompted to do so.
</p>
<br />


<p>
<img width="1027" height="695" alt="13" src="https://github.com/user-attachments/assets/b13b08be-5b54-4edf-b500-386e6f44befa" />
</p>


<p>
Next, we will have to register PHP in IIS Manager. Search Internet Information Services (IIS) Manager from the search bar by the start menu, right click and select "Run as Administrator".
</p>
<br />


<p>
<img width="1367" height="904" alt="14" src="https://github.com/user-attachments/assets/a025cf92-882d-4228-9325-7270847a6ded" />

</p>


<p>
Click on the "..." next to the text box and select the "php-cgi.exe" file found in the PHP folder we had extracted the php files into in the earlier steps (C:\PHP). This will finalize the link between PHP and IIS.
</p>
<br />


<p>
<img width="1911" height="557" alt="15" src="https://github.com/user-attachments/assets/2d4b4268-cbfb-48ad-9341-fb5656c76834" />

</p>


<p>
Now we will refresh IIS to update it's PHP registration. First we will click on the "osticket-vm" tab on the lefthand side of the IIS Manager to get to the home page. Once there, we will hit "Stop" and then "Start" to restart the IIS manager. 
</p>
<br />


<p>
<img width="888" height="1100" alt="17" src="https://github.com/user-attachments/assets/e47cf908-1117-4ca3-99bf-56303bbfab2e" />

</p>


<p>
The next step involves the installation of the OsTicket application from the zip folder "osTicket-v1.15.8.zip" found in the OsTicket-Installation-Files folder. First, we will extract the zip folder "osTicket-v1.15.8.zip". Then we will copy the "upload" folder and paste it into the "wwwroot" folder found in the following filepath (C:\inetpub\wwwroot). Then we will rename the pasted folder to "OsTicket".
</p>
<br />


<p>
<img width="1906" height="429" alt="18" src="https://github.com/user-attachments/assets/8d47d2fe-c5de-4705-97f4-54de6e453a6d" />
<img width="966" height="706" alt="19" src="https://github.com/user-attachments/assets/d324f131-9e75-4dd4-a298-26085400e794" />


</p>


<p>
Once the above has been completed, we will refresh the IIS Manager per the instructions mentioned previously. Now we will enable certain PHP extensions to meet OsTicket qualifications and requirements. Within the IIS Manager homepage, we will select PHP Manager under the "osticket-vm" tab on the left hand side of the page. Then we will click on "Disable or enable an extension" 
</p>
<br />


<p>
<img width="712" height="470" alt="20" src="https://github.com/user-attachments/assets/8a07c2f6-5ddf-4e95-84d7-1afdf92aedb1" />

</p>


<p>
After clicking this, we will enable the following extensions:
  - php_imap.dll
  - php_intl.dll
  - php_opcache.dll

Once the above have been enabled, we can refresh IIS Manager to ensure proper functionality.

</p>
<br />

<img width="795" height="475" alt="21" src="https://github.com/user-attachments/assets/afa52f64-2bb4-4f48-bae3-7865b38cc5b7" />

<p>
Next, in File Explorer, we are going to rename the "ost-sampleconfig.php" file located in the following file path (C:\inetpub\wwwroot\osTicket\include) to display "ost-config.php". Omitting the "sample" part of the file name.
</p>
<br />

</p>
<br />


<img width="364" height="507" alt="image" src="https://github.com/user-attachments/assets/3f9cdac7-22d4-4481-9be5-f0f9b65b9aa4" />

<p>
Once the file has been renamed, we will adjust it's permissions settings to grant everyone access by doing the following. First we will right-click on the "ost-config.php" file and select properties. Click on the Security tab at the top and select "Advanced" 
</p>
<br />
</p>
<br />


<img width="758" height="144" alt="22" src="https://github.com/user-attachments/assets/d43a2aa7-a381-4f1d-a34a-3ef04388f079" />

<p>
Next, we will click on "Disable Inheritance" found on the bottom left of the "Advanced Security Setting for ost-config.php" pop-up window. You will be prompted with a message asking to "Remove all inherited permissions", we will select that to remove all inherited permissions.
</p>
<br />

<img width="797" height="328" alt="23" src="https://github.com/user-attachments/assets/4032db12-9895-49fa-9070-89fb95e46b43" />

<p>
In order to enable permissions or add permissions for everybody, in this case, we can select "Add" in the "Advanced Security Setting for ost-config.php" pop-up window. Next we will click "Select a principal" and enter "Everyone" in the text box under "Enter the object name to select". Click "Check Names" and then "OK".
</p>
<br />

<img width="425" height="399" alt="24" src="https://github.com/user-attachments/assets/f1bf3c04-0d9f-4956-b389-e9b9bbbfa534" />

<p>
Next, under the basic permissions window, we can configure the types of permissions enabled, depending on the group/ object name selected. In this case, we will select all of the permissions for everyone and press "Ok". Generally, having such permissions allowed for everyone isn't the most secure approach, but for lab purposes we will proceed.
</p>
<br />

<img width="1899" height="445" alt="25" src="https://github.com/user-attachments/assets/abccfdf0-3a63-4bce-bd79-f70087a9ff2c" />

<p>
Lastly, we can navigate to our OsTicket browser by doing the following steps. First, navigate back to the IIS Manager home page and click on the drop down named "osticket-vmd" -> click on the "Sites" dropdown -> click on the "Default Web Site" drop down -> click on the "osTicket" tab. From here we will click on "Browse*:80 (http)" located on the far right side under "Manage Folder" and "Browse Folder". This opens up the following link on your VM's default browser (http://localhost/osTicket/).
</p>
<br />

<img width="1245" height="622" alt="26" src="https://github.com/user-attachments/assets/8f80aa5e-319e-43f6-865d-50eb0e74cd4b" />

<p>
You may now press continue on the browser and configure relative System settings, Admin User settings, and Database Settings. OsTicket installation has now been completed.
</p>
<br />
