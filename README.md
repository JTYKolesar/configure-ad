<p align="center">
<img src="https://i.imgur.com/CcM4XsW.png" height="55%" width="55%" alt="Microsoft Active Directory Logo"/>
</p>
<p align="justify">

<h1>Microsoft Azure - Active Directory (AD)</h1>

This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />
</p>

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>Configuration Steps</h2>

- Setup 2 Virtual Machines within Azure:
  - Domain Controller VM (Windows Server 2022) and Client VM (Windows 10) using same Resource Group and Vnet
  - Ensure Connectivity between the client and Domain Controller
- Install Active Directory Domain Services within Domain Controller VM
- Create an Admin and Standard User Account in AD
- Link Cilent VM to a domain
- Setup Remote Desktop for non-administrative users on Client VM
- Create additional users and attempt to log into Client VM as one of those users

<h2>Step Process</h2>

<h3>&#9312; Create a Domain Controller VM</h3>

- In the Search Box at the top header, type and select "Virtual machines".
  - If "Virtual machines" is already listed on the front page, then you can simply click on it, rather than manually searching.

<p>
<img src="https://i.imgur.com/tiC5aA4.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

- Name your Virtual Machine anyway you want (this example uses **DC-01**).
  - Resource Group is automatically given a name when naming the Virtual Machine, but you can change it if you wish (this example uses **DC-01_group**).
- Change the Region that best suites your location (this example uses **(US) West US 3**).
- Change the Image to a Windows Server, as this will become our Domain Controller VM (this example uses **Windows Server 2022 Datacenter: Azure Edition**).
- Make sure the Size is adequate enough to run this server (this example uses **Standard_E2s_v3 - 2 vcpus, 16 GiB memory**).
- Create a username of your choice and password (this example uses **dcuser**).
- IF there is a Licensing Checkbox at the end, make sure that is CHECKED!
- Skip everything else and click "Review + create".
- If Validation passed, click "Create".

<p>
<img src="https://i.imgur.com/AsbGinQ.png" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>
<hr>

<h3>&#9313; Create a Client VM</h3>

- Follow the same steps as before for creating a virtual machine.
  - However, the Resource Group should be assigned to the one created for the Domain Controller VM (this example uses **DC-01_group**).
- Change the Image to a Windows OS (this example uses **Windows 10 Pro, version 22H2 - x64 Gen2**)
- Once done, click "Next" until you reach "Networking" (OR you can simply click the Networking tab at the top).

<p>
<img src="https://i.imgur.com/2QaEfg9.jpg" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>

- The only purpose here is to make sure that the "Virtual network" is set to the Vnet that the Domain Controller VM automatically created (this example uses **DC-01-vnet**).
- Select the dropdown box for Subnet and confirm the default selection (this example uses **default (10.0.0.0/24)**).
  - Despite visually shown that the Subnet is set, you must manually confirm that configuration.
- Skip everything else and click "Review + create".
- If Validation passed, click "Create".

<p>
<img src="https://i.imgur.com/mnVSCa2.jpg" height="70%" width="70%" alt="Disk Sanitization Steps"/>
</p>

<hr>



<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<br />
