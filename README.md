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

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- Heidi SQL
- osTicket Installation files
  


<h2>Installation Steps</h2>

<p>
"<img width="926" height="1143" alt="1" src="https://github.com/user-attachments/assets/d8da117f-1d10-4e95-bd40-c3582172694c" />
</p>
<p>
To get started, we will first create a virtual machine. This virtual machine will be housed under a new Resource Group named "osTicket" and the virtual machine (VM) will be names "osticket-vm". When creating the VM, we will be selecting a Windows 10 image, the size of the virtual machine will contain at least 2 vcpus. Set username and password to your preference.
</p>
<br />

<p>
<img width="2740" height="6000" alt="2" src="https://github.com/user-attachments/assets/29faee31-2dd0-45cf-b1b6-0a534a67f93c" />

</p>
<p>
Once the VM has been created, we will copy the public IP address of the VM and paste it onto the Remote Desktop application. In the Remote Dekstop app, select show more options and enter in the username that was created in the first step.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once logged onto the virtual machine, we will open and download the following <a href="https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0/">OsTicket Installation Files. Once dowloaded, we will extract these files onto our VM's desktop.  
</p>
<br />
