<h1>Network File Shares and Permissions</h1>
This tutorial outlines how to setup network file sharing and permissions and how they effect a work enviroment.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Prerequisites<h2>

- Have already looked through and done [configuring active directory within azure VMs.](https://github.com/anthonyfigueroa-1/ActiveDirectory)

<h2>Steps</h2>

<p>
<img src="https://i.imgur.com/8rwJ0Js.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
  
<p>
<img src="https://i.imgur.com/PFEQZYu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

  - Create some sample file shares with various permissions
- Connect/log into DC-1 as your domain admin account (mydomain.com\jane_admin)
- Connect/log into Client-1 as a normal user (mydomain\<someuser>)
- On DC-1, on the C:\ drive, create 4 folders: “read-access”, “write-access”, “no-access”, “accounting”
- Set the following permissions (share the folder) for the “Domain Users” group:
- Folder: “read-access”, Group: “Domain Users”, Permission: “Read”
- Folder: “write-access”,  Group: “Domain Users”, Permissions: “Read/Write”
- Folder: “no-access”, Group: “Domain Admins”, “Permissions: “Read/Write”

  <br />
  
<p>
<img src="https://i.imgur.com/ejQ6D0s.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

  - Attempt to access file shares as a normal user
- On Client-1, navigate to the shared folder (start, run, \\dc-1)
- Try to access the folders you just created. Which folders can you access? Which folders can you create stuff in? Does it make sense?

  <br />
  
<p>
<img src="https://i.imgur.com/ujJGjLP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

  - Create an “ACCOUNTANTS” Security Group, assign permissions, an test access
- Go back to DC-1, in Active Directory, create a security group called “ACCOUNTANTS”
- On the “accounting” folder you created earlier, set the following permissions:
- Folder: “accounting”, Group: “ACCOUNTANTS”, Permissions: “Read/Write”
- On Client-1, as  <someuser>, try to access the accountants folder. It should fail. 
- Log out of Client-1 as  <someuser>
- On DC-1, make <someuser> a member of the “ACCOUNTANTS”  Security Group
- Sign back into Client-1 as <someuser> and try to access the “accounting” share in \\DC-1\ - Does it work now?
  
  <br />



