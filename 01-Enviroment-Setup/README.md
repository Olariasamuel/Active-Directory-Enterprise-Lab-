01 - Environment Setup
Overview
This phase covers the initial preparation of the Windows Server 2022 virtual machine before Active Directory deployment. This includes OS installation, server renaming, and static IP configuration.

Lab Environment
Component : Hypervisor VirtualBox 
Component : Operating System Windows Server 2022 Standard Evaluation
Component : CPU AMD Ryzen
Component : RAM 4 GB
Component : Disk 60 GB
Component : Network Internal Network (NAT)

Steps Performed
1. Windows Server 2022 Installation

Installed Windows Server 2022 Standard Evaluation on a VirtualBox VM
Completed initial setup and logged in as local Administrator

Screenshot: Initial Server Manager showing default hostname WIN-F9RIL65VKN0 and DHCP-assigned IP

2. Server Rename

Renamed the server from the default hostname to DC01 to reflect its future role as Domain Controller
Restarted the server to apply the name change

How to rename:
Server Manager → Local Server → Computer Name → Change

3. Static IP Configuration

Assigned a static IPv4 address to ensure consistent network identity, required for a Domain Controller

Network Configuration:
Setting           Value
IP Address      = 10.0.2.10
Subnet Mask     = 255.255.255.0
Default Gateway = 10.0.2.2
Preferred DNS   = 127.0.0.1

Note: DNS is set to 127.0.0.1 (loopback) because this server will host its own DNS service after AD DS promotion. This is the recommended configuration for a Domain Controller.

How to set static IP:
Server Manager → Local Server → Ethernet → 
Right-click adapter → Properties → IPv4 Properties

Result
At the end of this phase, the server is:

✅ Running Windows Server 2022
✅ Named DC01
✅ Configured with a static IP (10.0.2.10)
✅ DNS pointing to itself (127.0.0.1)
✅ Ready for Active Directory Domain Services installation


