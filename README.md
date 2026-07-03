# Active-Directory-Create-And-Organize-Users
Windows Server Active Directory (AD DS) home lab creating and establishing a domain and a scalable OU hierarchy with nested departmental security groups and role-based user assignment.

## Enviroment & Specifications:
* **Goal**: Set up a centralized Active Directory domain structure by creating departmental Organizational Units (OUs), provisioning individual user accounts within those departments, and establishing matching Security Groups to handle role-based user access.
* **Platform**: VMware Workstation (VMnet4 Host-Only) using Windows Server 2022 and Windows 11 Pro.
* **Network Types**: Host-Only (VMnet4) treated as a “sandbox” for isolation.
* **Subnet**: 192.168.100.0/24 with DHCP disabled.

---

## 1. Domain Creation and Active Directory Installation

Installed Windows Server and Initiated the Active Directory Domain Services (AD DS) Configuration Wizard to promote the server to a Domain Controller and named it "lab.nate.com".

The "lab.nate.local" Root Domain Name(Created Domain.png)
