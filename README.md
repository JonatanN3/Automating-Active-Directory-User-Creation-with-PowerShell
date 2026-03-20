<p align="center">
<img width="600" height="335" alt="image" src="https://github.com/user-attachments/assets/f5a3d652-196e-4dcf-814f-113a9cbb6f54" />



<h1>Automating Active Directory User Creation with PowerShell</h1>
This tutorial focuses on establishing the necessary infrastructure in Microsoft Azure for an Active Directory deployment. This includes creating the required cloud resources, configuring a virtual network, deploying virtual machines, and confirming proper network communication between systems before implementing Active Directory Domain Services.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Active Directory Domain Services (AD DS)
- Active Directory Users and Computers (ADUC)
- Windows PowerShell ISE
- Active Directory PowerShell Module
- Remote Desktop Protocol (RDP)


<h2>Operating Systems Used</h2>

- Windows Server 2022 (Domain Controller: DC-1)
- Windows 11 (Client Machine: Client-1)

<h2>Open and Review the PowerShell Script</h2>

<img width="1536" height="1024" alt="LabB5" src="https://github.com/user-attachments/assets/ea37d4dd-bbd6-4bad-83ad-d6af1f2fbcc9" />
</p>
<p>
Steps:
   
- Launch **Windows PowerShell ISE** with administrative privileges.
- Import or open the user creation script within the script editor.
- Examine the script variables and configuration details carefully.
- Verify the password that will be applied to the generated user accounts.
- Check the total number of users the script is configured to create.
- Go through the overall script layout to ensure everything is correct before running it.

**Explanation**
This step represents the verification stage of the automation process. Reviewing the newly created accounts in Active Directory confirms that the script executed correctly and that all users were added to the appropriate groups and locations.

<h2>Review the New-ADUser Automation Logic</h2>

<img width="1536" height="1024" alt="LabB7" src="https://github.com/user-attachments/assets/441fcb41-940d-4f32-a998-6e651ebc19d6" />
</p>
<p>
Steps:
  
- Examine the portion of the script that handles the creation of user accounts.
- Ensure that a loop is implemented to generate multiple users automatically.
- Check that first and last names are being generated programmatically.
- Verify that these names are combined properly to form a username.
- Review the method used to convert the password into a secure string format.
- Confirm that the **New-ADUser** cmdlet is being used to create each user account.
- Ensure the **Path** parameter is set to the **_EMPLOYEES** Organizational Unit.
- Verify that all newly created accounts are set to active (enabled).

**Explanation:**
This step demonstrates the practical use of scripting for scalability. Automating user creation allows administrators to quickly deploy large numbers of accounts while maintaining standardized configurations and minimizing human error.

<h2>Execute the Script and Create User Accounts</h2>

<img width="1536" height="1024" alt="LabB8" src="https://github.com/user-attachments/assets/f755d8b7-f5e1-4541-8df0-2461fae52572" />
</p>
<p>
Step:

- Click **Run Script** in PowerShell ISE.
- Watch the console output at the bottom of the window.
- Confirm that usernames are being generated one after another.
- Allow the script to continue until the required number of users are created.

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
