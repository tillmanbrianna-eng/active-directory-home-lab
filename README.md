# Active Directory Home Lab

## Overview
This project is a virtual Active Directory home lab built in VMware Workstation. I used Windows Server 2025 as a domain controller and a Windows 11 Pro machine as the client to simulate a small business network. The lab includes Active Directory setup, DNS configuration, basic networking, and joining a device to a domain to practice system administration skills.

## Environment

- Virtualization Platform: VMware Workstation
- Network Type: Host-Only
- Domain Controller: Windows Server 2025 (DC01)
- Client Machine: Windows 11 Pro
- Domain Name: homelab.local
  
## Objectives

- Build a virtual Active Directory environment using VMware Workstation
- Install and configure Windows Server 2025 as a Domain Controller (DC01)
- Configure DNS to support domain name resolution
- Join a Windows 11 Pro client to the domain (homelab.local)
- Organize users and computers using Active Directory Organizational Units (OUs)
- Practice basic network configuration and validation testing

## Network Architecture

![Network Diagram](screenshots/network-diagram/active-directory-network-diagram.png)

## VMware Setup

The virtual lab environment was built using VMware Workstation with two virtual machines: a Windows Server 2025 Domain Controller (DC01) and a Windows 11 Pro client machine. A NAT network was used to allow internet access while still enabling communication between both systems.

Both virtual machines were configured with appropriate CPU, memory, and storage resources to simulate a small enterprise environment.

### VM Creation (Server)
![VM Creation - Server](screenshots/vmware/vmware-server-vm-creation.png)

### VM Creation (Windows 11)
![VM Creation - Windows 11](screenshots/vmware/vmware-windows-vm-creation.png)

### Windows Server Edition Selection
![Server GUI Selection](screenshots/vmware/windows-server-gui-selection.png)

### Windows 11 Pro Selection
![Windows 11 Pro Selection](screenshots/vmware/windows-11-pro-selection.png)

### VMware Network Settings
![Network Adapter Settings](screenshots/vmware/vmware-network-adapter-settings.png)

### Virtual Network Editor
![Virtual Network Editor](screenshots/vmware/vmware-virtural-network-editor.png)

### VM Overview
![VM Overview](screenshots/vmware/vmware-vm-overview.png)

## Networking Configuration

The network was configured using a NAT virtual network in VMware Workstation, allowing both virtual machines to communicate with each other while maintaining internet access.

The Domain Controller (DC01) was configured with a static IP address to ensure consistent network identification and support Active Directory services. The Windows 11 client was configured to use the Domain Controller as its primary DNS server to allow proper domain name resolution within the environment.

### Domain Controller IP Configuration
![DC IP Config](screenshots/networking/dc-static-ip-config.png)

### Windows 11 IP Configuration
![Client IP Config](screenshots/networking/client-ipconfig-all.png)

### Connectivity Test (Ping)
![Ping Test](screenshots/networking/successful-ping-test.png)

## Active Directory Setup

Active Directory Domain Services (AD DS) was installed on the Windows Server 2025 virtual machine (DC01). The server was then promoted to a Domain Controller and configured with the homelab.local domain.

DNS services were installed alongside Active Directory to support domain name resolution and authentication within the environment.

### Active Directory Domain Services Installation
![AD DS Installation](screenshots/active-directory/ad-ds-installation.png)

### Domain Controller Promotion
![DC Promotion](screenshots/active-directory/domain-controller-promotion.png)

## DNS Configuration

DNS was configured on the Domain Controller (DC01) during the Active Directory Domain Services installation process. A forward lookup zone for homelab.local was automatically created to support name resolution within the environment.

The Windows 11 client machine was configured to use the Domain Controller as its primary DNS server to allow successful domain communication and authentication.

### Forward Lookup Zone
![homelab.local Zone](screenshots/dns/forward-lookup-zone.png)

## Organizational Units (OUs)

Organizational Units (OUs) were created within Active Directory Users and Computers to organize domain resources and simulate a structured enterprise environment.

### Organizational Unit Structure
![OU Structure](screenshots/ous/organizational-units.png)

## Users and Groups

User accounts and security groups were created within Active Directory Users and Computers to simulate user management in an enterprise environment.

These accounts were used to test authentication, domain login functionality, and resource organization within the homelab.local domain.

### Domain User Accounts
![Domain Users](screenshots/users-groups/domain-users.png)

### Security Groups
![Security Groups](screenshots/users-groups/security-groups.png)

## Validation and Domain Authentication

The Windows 11 Pro client machine was successfully joined to the homelab.local domain and validated through multiple authentication and connectivity tests.

Network communication, DNS resolution, and domain authentication were verified to confirm proper Active Directory functionality within the lab environment.

### Domain Membership Verification
![Domain Membership](screenshots/validation/client-domain-membership.png)

### Domain Authentication Validation
![whoami Validation](screenshots/validation/domain-verification.png)

## Computer Management (OU Placement)

After the Windows 11 client machine was joined to the homelab.local domain, the computer object was managed through Active Directory Users and Computers.

The client computer was moved into the appropriate Organizational Unit (OU) to simulate structured resource management within an enterprise Active Directory environment.

### Default Computer Container
![Default Container](screenshots/computer-management/ad-computer-default-container.png)

### Moving Computer Object to OU
![Move Computer](screenshots/computer-management/ad-move-computer-to-computer-ou.png)

### Computer Object in Organizational Unit
![Final OU Placement](screenshots/computer-management/ad-computer-in-computer-ou.png)

## Summary / Lessons Learned

This project was a hands-on Active Directory home lab built using VMware Workstation. I set up a Windows Server 2025 machine as a Domain Controller (DC01), configured DNS, and joined a Windows 11 Pro client to the domain homelab.local.

While building this lab, I got practical experience with how Active Directory actually works in a small network. This included setting up DNS so the domain could function properly, configuring a NAT network so the machines could communicate, and managing users, computers, and organizational units inside Active Directory.

One of the biggest takeaways was understanding how important DNS is in a domain environment. I also learned how structure matters inside Active Directory, especially when organizing computers and users into OUs instead of leaving everything in the default container.

Overall, this project helped me connect the theory of Windows networking and Active Directory with real hands-on practice, and it made the whole system make a lot more sense.
