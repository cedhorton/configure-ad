<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Deployed in the Cloud (Azure)</h1>
This walkthrough outlines the implementation of Active Directory within Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Setup Resources In Azure
- Ensure Connectivity Between the Client and Domain Controller
- Installed Active Directory
- Created an Admin and Normal User Account in AD
- Joined Client to Domain
- Setup Remote Desktop for non-administrative users on Client
- Created a bunch of additional users and attempted to log into Client with one of the users

 

<h2>Deployment and Configuration Steps</h2>

![image](https://github.com/cedhorton/configure-ad/assets/173581553/b296cf91-a977-4c78-b740-6dcaf6ba8abb)

<p>Setup resources in Azure for the domain controler and client to run active directory.
</p>
<br />


![image](https://github.com/cedhorton/configure-ad/assets/173581553/7a1e4dda-6497-4083-9021-4083296ca3e2)

<p>
Logged in to Client-1 with Remote Desktop to ping DC-1’s private IP address with ping -t <ip address> (perpetual ping). Logged in to the Domain Controller and enable ICMPv4 in the local windows Firewall. Checked back at Client-1 to see the ping succeed.

</p>
<br />

![image](https://github.com/cedhorton/configure-ad/assets/173581553/6dd08fec-9b84-4f4b-988a-ded0df31363b)

<p>
Logged in to Domain Controller and installed Active Directory Domain Services.
</p>
<br />

![image](https://github.com/cedhorton/configure-ad/assets/173581553/a7267f09-89c7-4601-834e-302e449ef17f)

<p>
In Active Directory Users and Computers (ADUC), I created an Organizational Unit (OU) called “_EMPLOYEES”,
Created a new OU named “_ADMINS”,
Created a new employee named “Jane Doe” with the username of “jane_admin” and
added jane_admin to the “Domain Admins” Security Group.
</p>
<br />

![image](https://github.com/cedhorton/configure-ad/assets/173581553/a6e9ec13-6c08-47a1-9242-6e139bb4c634)

<p>
From the Azure Portal, I set the Client’s DNS settings to the Domain Controler’s Private IP address. I then logged in to the Client (Remote Desktop) as the original local admin (labuser) and joined it to the domain. I
logged in to the Domain Controller (Remote Desktop) and verified that the Client showed up in Active Directory Users and Computers (ADUC) inside the “Computers” container on the root of the domain.

</p>
<br />

![image](https://github.com/cedhorton/configure-ad/assets/173581553/8c95c896-e433-4590-81db-a7eb9d04ebbe)

<p>
Allowed “domain users” access to remote desktop.
</p>
<br />

![image](https://github.com/cedhorton/configure-ad/assets/173581553/a4a27969-7233-4570-8a90-1dd2d184911a)

<p>
Ran script and created a bunch of random users as "employees".
</p>
<br />


