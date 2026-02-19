# Active Directory Home Lab 

## Overview
Built an Active Directory home lab using two virtual machines:
- **Windows Server 2019** as the **Domain Controller (AD DS + DNS)**
- **Windows 10 Enterprise** as a **domain-joined client**
The Domain Controller uses **two virtual NICs** to support an isolated internal network for the client while still enabling **internet access**.

## Lab Topology
- **DC (Server 2019)**
  - NIC 1: Internal / Private LAN (DC ↔ Client)
  - NIC 2: External / NAT/Bridged (Outbound internet)
- **Client (Windows 10 Enterprise)**
  - Connected to Internal LAN
  - DNS points to the DC

> Add your diagram here:  
![Topology](docs/topology.png)

## Key Features
- Created a Windows domain and promoted Server 2019 to a Domain Controller
- Configured **AD DS + DNS**
- Created domain users with unique credentials
- Joined Windows 10 client to the domain
- Verified domain login and connectivity

## Validation (Proof of Working)
- Client successfully joined the domain
- Domain user login works on Windows 10
- DNS resolution works for domain resources
- Client has internet access through the lab network design

## Report Pages
- [Skills Learned](docs/skills_learned.md)
- Virtualization & virtual networking (internal vs NAT/bridged)
- Windows Server administration fundamentals
- Active Directory (AD DS) and Domain Controller concepts
- DNS fundamentals for AD environments
- Identity & Access Management (users, groups, OUs)
- Networking: IP addressing, gateways, routing/NAT concepts
- Troubleshooting domain join / authentication issues

## Troubleshooting Notes
See: [docs/troubleshooting.md](docs/troubleshooting.md)

## Possible Improvements
- Add Group Policy (GPO) enforcement (password/lockout policies)
- Add DHCP on the internal network
- Add file shares with group-based permissions
- Add logging/auditing and explore security monitoring
