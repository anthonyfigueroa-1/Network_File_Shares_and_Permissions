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
<img src="https://i.imgur.com/aydK00C.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
