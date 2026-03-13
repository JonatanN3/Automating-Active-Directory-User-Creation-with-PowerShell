<p align="center">
<img width="600" height="335" alt="image" src="https://github.com/user-attachments/assets/f5a3d652-196e-4dcf-814f-113a9cbb6f54" />



<h1>Automating Active Directory User Creation with PowerShell</h1>
This tutorial focuses on establishing the necessary infrastructure in Microsoft Azure for an Active Directory deployment. This includes creating the required cloud resources, configuring a virtual network, deploying virtual machines, and confirming proper network communication between systems before implementing Active Directory Domain Services.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Azure Virtual Network
- Azure Resource Groups
- Remote Desktop Protocol (RDP)
- DNS

<h2>Operating Systems Used </h2>

- Windows Server 2022 (Datacenter Azure Edition Hotpatch-x64 Gen2)
- Windows 11 Pro (Version 25H2-x64)
  

<h2> Open and Review the PowerShell Script</h2>

<img width="1536" height="808" alt="Lab1" src="https://github.com/user-attachments/assets/10ef2fe8-9079-4ceb-aa6a-35ab6405fb09" />
</p>
<p>
Steps:
  
Open Windows PowerShell ISE as Administrator.
Load the user creation script.
Review the configuration variables at the top of the script.
Confirm the password value and number of accounts to generate.
Confirm the script points to the correct Organizational Unit path.

Why this step matters
This is the preparation stage. It ensures the script is configured correctly before user accounts are created in bulk.


<h2>Configure the Script to Use New-ADUser</h2>

<img width="1536" height="810" alt="Lab2" src="https://github.com/user-attachments/assets/8934d166-7e95-4b85-9004-757912121816" />
</p>
<p>
Steps:
  
Define a loop to repeat the process for the total number of users.
Generate a random first name.
Generate a random last name.
Combine them into a username format.
Convert the password into a secure string.
Use New-ADUser to create the account.
Set the Path parameter so the account is created inside _EMPLOYEES.
Keep the account enabled so it can be used immediately.

Why this step matters
This is the core automation step. It removes the need to manually create users one by one and places them directly into the correct Organizational Unit.


<h2>Run the Script and Begin Creating Accounts</h2>

<p><img width="1536" height="802" alt="Lab4" src="https://github.com/user-attachments/assets/fd65a346-5a87-4320-a7cb-066a851c47b5" />

</p>
<p>
Step:

Click Run Script in PowerShell ISE.
Watch the console output at the bottom of the window.
Confirm that usernames are being generated one after another.
Allow the script to continue until the required number of users are created.

Why this step matters
This proves that the script is not just written — it is actually executing and creating users in Active Directory.

<h2>Verify Users in Active Directory Users and Computers</h2>

<p>
  
<img width="1536" height="870" alt="560603103-a45e8255-76a3-4ed1-a028-6df06d804b44" src="https://github.com/user-attachments/assets/3d6f272c-7e8c-4382-9d66-ee0da1d919b1" />
</p>
<p>
Steps:
  
Open Active Directory Users and Computers.
Expand the domain.
Open the _EMPLOYEES Organizational Unit.
Scroll through the list of users.
Confirm that many accounts now appear in the OU.

Why this step matters
This is the proof stage. It confirms the accounts were actually written into Active Directory and stored in the correct location.


<h2>Open a User and Verify Group Membership</h2>

<p>
<img width="1536" height="865" alt="Lab6" src="https://github.com/user-attachments/assets/b364fc50-8644-45ac-9dec-d837abed3df9" />
</p>
<p>
Step:
  
In Active Directory Users and Computers, select one of the generated users.
Right-click the account and choose Properties.
Open the Member Of tab.
Confirm the user belongs to the default Domain Users group.

Why this step matters
This confirms the account is a valid domain user and has the expected default membership after creation.


<h2> Log In with a Generated User Account</h2>

<p>
<img width="1536" height="862" alt="Lab7" src="https://github.com/user-attachments/assets/16a7de95-3c73-495c-b2cb-463c2ee8f7ff" />
</p>
<p>
Steps:
  
Open Remote Desktop Connection or access the client machine.
Enter the username of one of the generated users.
Type the assigned password from the script.
Sign in to the client computer.
Confirm the desktop loads successfully under that user profile.

Why this step matters
This is the final validation step. It proves the accounts created by the PowerShell script are fully functional and can authenticate against Active Directory.


<h2>Summary</h2>
