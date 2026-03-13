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
  

<h2>Open Resource Groups in Azure</h2>

<img width="1536" height="808" alt="Lab1" src="https://github.com/user-attachments/assets/10ef2fe8-9079-4ceb-aa6a-35ab6405fb09" />
</p>
<p>
Steps:
  
- Open in to the Azure portal.
- Locate Resource groups from the Azure services menu.
- Click Create to begin building a new resource group for the lab environment.

Explanation:
  A resource group is used to organize related Azure resources in one location. Creating it first helps keep all lab components structured and easier to manage.

<h2>Create the Resource Group</h2>

<img width="1536" height="810" alt="Lab2" src="https://github.com/user-attachments/assets/8934d166-7e95-4b85-9004-757912121816" />
</p>
<p>
Steps:
  
- Select the appropriate Azure subscription.
- Click the resource group name Active-Directory-Lab.
- Choose the region Canada Central.
- Review the settings.
- Continue to create the resource group.

Explanation:
This creates a dedicated container for all resources used in the lab, including virtual machines and networking components.

<h2>Create the Virtual Network</h2>

<p><img width="1536" height="802" alt="Lab4" src="https://github.com/user-attachments/assets/fd65a346-5a87-4320-a7cb-066a851c47b5" />

</p>
<p>
Step:

- Launch Virtual networks in Azure.
- Select Create.
- Assign the network to the Active-Directory-Lab resource group.
- Enter the virtual network name Active-Directory-VNet.
- Verify the region is the same as the resource group.
- Review the default IP address space and subnet settings.
- Click Create.

Explanation:
 The virtual network allows the domain controller and client machine to communicate privately inside Azure. This is required for domain communication and DNS resolution.

<h2> Begin Creating the Domain Controller VM</h2>

<p>
  
<img width="1536" height="870" alt="560603103-a45e8255-76a3-4ed1-a028-6df06d804b44" src="https://github.com/user-attachments/assets/3d6f272c-7e8c-4382-9d66-ee0da1d919b1" />
</p>
<p>
Steps:
  
- Open Virtual machines in Azure.
- Click Create virtual machine.
- Select the Active-Directory-Lab resource group.
- Enter the VM name dc-1.
- Select the deployment region Canada Central. (The same as the resource group)
- Review the basic configuration settings.

Explanation:
 This virtual machine is to serve as the main server for the lab. It will be promoted to a Domain Controller.

<h2>Configure dc-1 Operating System and Credentials</h2>

<p>
<img width="1536" height="865" alt="Lab6" src="https://github.com/user-attachments/assets/b364fc50-8644-45ac-9dec-d837abed3df9" />
</p>
<p>
Step:
  
- Select Windows Server 2022 Datacenter Azure Edition as the image.
- Confirm the VM architecture is set to x64.
- Select the VM size for the lab.
- Type the administrator username.
- Enter and confirm the administrator password.
- Continue through the setup wizard.

Explanation:
This step confirms that the server is deployed with a supported Windows Server operating system capable of running Active Directory Domain Services.

<h2>Configure Networking for dc-1</h2>

<p>
<img width="1536" height="862" alt="Lab7" src="https://github.com/user-attachments/assets/16a7de95-3c73-495c-b2cb-463c2ee8f7ff" />
</p>
<p>
Steps:
  
- Open the Networking tab during the dc-1 VM creation.
- Select Active-Directory-VNet as the virtual network.
- Choose default subnet.
- Assign a public IP address for remote access.
- Set the network security group options.
- Allow RDP (3389) inbound access.
- Review the settings before deployment.

Explanation:
This ensures that DC-1 is connected to the lab environment and can be remotely accessed and managed via Remote Desktop.

<h2>Summary</h2>
