<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1 : Setup Resources in Azure
- Step 2 : Install Active Directory
- Step 3 : Create an Admin and Normal User Account in AD
- Step 4 : Setup Remote Desktop for non-administrative users on Client-1
- Step 5 : Create a bunch of additional users and attempt to log into client-1 with one of the users

<img src="https://github.com/JoeyGutierrez760/configure-ad/assets/41347751/80ad7815-21e1-4e52-a92d-51acb8f502f7" height="80%" width="80%" alt="Disk Sanitization Steps"/>


<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://github.com/JoeyGutierrez760/configure-ad/assets/41347751/b36fee9f-f5aa-4fc9-a1f4-beb04a61b964" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To start Active Directory, begin by logging into the server named "DC-1". Once logged in, proceed with the installation of Active Directory Domain Services. After the installation, promote the server as a domain controller, setting up a new forest with the desired domain name, such as "mydomain.com". Remember to take note of the chosen domain name for future reference. Following the promotion, restart the server to apply the changes. Finally, log back into the server as the user "mydomain.com\labuser" to access the Active Directory environment and begin managing the domain.
</p>
<br />

<p>
<img src="https://github.com/JoeyGutierrez760/configure-ad/assets/41347751/a10259e1-1708-4e48-890b-dc8784663d89" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To begin managing Active Directory, open Active Directory Users and Computers (ADUC) and create two Organizational Units (OU): one named "_EMPLOYEES" and another named "_ADMINS". Within "_EMPLOYEES", create a new employee named "Jane Doe" with the username "jane_admin" and assign the same password as the others. Next, add "jane_admin" to the "Domain Admins" Security Group. Afterward, log out or close the Remote Desktop connection to DC-1 and log back in as "mydomain.com\jane_admin". From now on, use "jane_admin" as your administrative account to manage the Active Directory environment.
</p>
<br />

<p>
<img src="https://github.com/JoeyGutierrez760/configure-ad/assets/41347751/a9ff12c5-7e85-4e40-8d0b-7e796bd61c03" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To initiate Active Directory, run the provided script and observe as it creates the accounts. Once the script completes, open Active Directory Users and Computers (ADUC) and verify that the accounts are present in the correct Organizational Unit (OU). To test the functionality, attempt to log into "Client-1" using one of the created accounts, taking note of the password specified in the script. This will ensure that the account creation and login processes are functioning as intended within the Active Directory environment.
</p>
<br />
