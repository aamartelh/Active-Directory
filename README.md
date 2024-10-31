<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Resetting a User’s Password in Active Directory</h1>
This tutorial outlines the steps for resetting a user’s password in Microsoft Active Directory within an on-premises environment or within an Active Directory setup on Azure.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (if using Virtual Machines/Compute in the cloud)
- Remote Desktop (for access to VMs)
- Active Directory Domain Services

<h2>Operating Systems Used </h2>

- Windows Server 2022, 2 vCPUs, 8 GB RAM (domain controller setup)
- Windows 10 Pro (22H2), 2 vCPUs, 8 GB RAM (client machine)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1: Access Active Directory Users and Computers
- Step 2: Locate and Select the User Account
- Step 3: Reset the User’s Password

<h2>Deployment and Configuration Steps</h2>

<p>
This tutorial assumes that an Active Directory environment is already set up with a domain controller on a server machine (DC-1) and a client machine (Client-1) joined to the domain.
  
  Step 1: Access Active Directory Users and Computers on DC-1
After logging into DC-1 (the domain controller machine), open Server Manager. From there, click on Tools in the top-right menu and select Active Directory Users and Computers.

![1](https://github.com/user-attachments/assets/c856c648-19e2-44cb-be62-c034fce54ee8)




Step 2: Locate the User Account
In Active Directory Users and Computers, navigate to your domain (e.g., mydomain.com). Expand the domain tree and locate the Organizational Unit (OU) where the user account is stored (e.g., _EMPLOYEES or _ADMINS). In this case, the user I am looking for will be found in "_EMPLOYEES". Right-click the "_EMPLOYEES" OU and select "Find". 

![2](https://github.com/user-attachments/assets/b1464bd2-f3d9-4353-a450-a9d3fe0cc403)



Step 3: Select the User and Initiate the Password Reset

Right-click on the user account (e.g., first.last) and choose Reset Password from the context menu.
A dialog box will appear, prompting you to enter a new password and confirm it. Ensure the User must change password at next logon option is selected if the user should create a new password upon their next login.


![3](https://github.com/user-attachments/assets/670e8816-7971-4a0b-beac-81195975d532)



![4](https://github.com/user-attachments/assets/369b07b6-32b2-4031-b4e8-e66da4c2d9c8)



Step 4: Confirm Password Reset
Click OK to save the new password. You should see a confirmation message indicating that the password was successfully reset. Inform the user of their temporary password if needed.


![5](https://github.com/user-attachments/assets/47a9985e-17ec-4a94-abf8-9c3f2535df09)
</p>
<br />
<p>

![6](https://github.com/user-attachments/assets/448d2ba7-6f49-4405-9526-b24201e19e9b)
</p>
<br />


Now, we'll try to log into our Client-1 machine with the new password



Go to Client-1 and attempt to log in as the user whose password was reset.
</p>
<br />
<p>

![7](https://github.com/user-attachments/assets/59960634-8532-4db3-ba7c-79bc60148185)
</p>
<br />

</p>
<br />
<p>

</p>
<p>
If User must change password at next logon was selected, the user should be prompted to set a new password after the first login. 

Although Jane Doe is in a OU called _ADMINS, she technically is not yet a Domain admin since we have not given those privileges to her. So to do this, we click on _ADMINS and see that Jane Doe is there. Right click on Jane Doe -> Properties -> Member Of then type in Domain Admins in the box. Click on Check names, then OK and apply these settings.
</p>
<br />
<p>

</p>
<br />
