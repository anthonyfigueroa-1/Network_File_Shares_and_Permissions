<h1>Network File Shares and Permissions</h1>
This tutorial outlines how to setup network file sharing and permissions and how they effect a work enviroment.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Prerequisites<h2>

- Have already looked through and done [Configuring Active Directory within Azure VMs](https://github.com/anthonyfigueroa-1/ActiveDirectory)

<h2>Steps</h2>

<p>
<img src="https://i.imgur.com/aydK00C.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

  - Login to Client-1 with Remote Desktop and ping DC-1’s private IP address with ping -t <ip address> (perpetual ping)
- Login to the Domain Controller and enable ICMPv4 in on the local windows Firewall
- Check back at Client-1 to see the ping succeed

  <br />
