# Active-Directory-Create-And-Organize-Users-Lab
Windows Server Active Directory (AD DS) home lab creating and establishing a domain and a scalable OU hierarchy with nested departmental security groups and role-based user assignment.

## Enviroment & Specifications:
* **Goal**: Set up a centralized Active Directory domain structure by creating departmental Organizational Units (OUs), provisioning individual user accounts within those departments, and establishing matching Security Groups to handle role-based user access.
* **Platform**: VMware Workstation (VMnet4 Host-Only) using Windows Server 2022 and Windows 11 Pro.
* **Network Types**: Host-Only (VMnet4) treated as a “sandbox” for isolation.
* **Subnet**: 192.168.100.0/24 with DHCP disabled.

---

## 1. Domain Creation and Active Directory Installation

Installed Windows Server and Initiated the Active Directory Domain Services (AD DS) Configuration Wizard to promote the server to a Domain Controller and named it "lab.nate.com".

![](Created%20Domain.png)

## 2. Joined Windows 11 Client to Domain
After installing Windows Server and deploying Active Directory Domain Services and promoting it to a Domain Controller I set up a Windows 11 Client and joined it to the "lab.nate.com" domain.

![](Joined%20Client%20to%20Domain.png)

## 3. Created Department Organizational Units
On the Windows Server in the Active Directory Users and Computers console, I created four Organizational Units (Accounting, Human Resources, Marketing, and Sales) under a top-level Organizational Unit named "HQ".

![](Created%20OUs.png)

## 4. Created Users in Organizational Units
By right-clicking on the target departmental Organizational Unit, hovering over "New", and clicking "User", I initiated the creation of a new user object. I input the users first and last name along with their User Principal Name (UPN) logon credentials. Finally, I established a temporary password, enforced the "User must change password at next logon" security baseline, and completed the account provisioning.

![](Created%20User%20Names.png)
![](Created%20User%20Passwords.png)
![](Finished%20Creating%20Users.png)

## 5. Directory Structure Overview
After provisioning the "HQ" top-level Organizational Unit, creating the departmental OUs, and populating them with their respective user accounts, this is the resulting directory tree structure.

![](Hierarchy%20of%20UsersOUs.png)

## 6. Created Security Groups
Within each departmental OU, I created a corresponding Security Group to facilitate role-based access control and streamline permission management for those specific business units.

![](Created%20Security%20Group.png)

## 7. Assigning Users to Security Groups
There are two ways to add a user to a security group within the console. One method is to open the Security Group's properties, navigate to the "Members" tab, and add the user accounts directly. Alternatively, you can open an individual user's properties, navigate to the "Member Of" tab, and associate the target Security Group with that user.

![](Added%20Users%20to%20SG.png)
![](Added%20Users%20to%20SG%202.png)

## 8. Remediating Group Assignment Errors (Troubleshooting)
Accidentally, I added two users from the Accounting OU to the Sales Security Group. To remediate this misconfiguration, I removed the Accounting users from the Sales Security Group and properly associated them with the Accounting Security Group instead. During this process, Active Directory generated a warning message confirming the removal of the objects from the group membership, which I accepted to finalize the fix.

![](Assigned%20Users%20to%20Wrong%20SG.png)
![](Warning%20of%20Removing%20Users.png)

## 9. Final Directory Structure Overview
After provisioning the top-level OU and the departmental OUs, along with populating the users and security groups, this is the resulting directory tree structure.

![](Results%20of%20Users%20and%20SGs.png)

## 10. User Authentication Verification
After successfully deploying the OUs, provisioning the user accounts, and structuring the security groups, I verified the configuration by executing test logons for the new user profiles. This confirmed that the network accounts can successfully authenticate against the Domain Controller.

![](Result%20of%20Signed%20In%20User.png)
![](Result%20of%20Signed%20In%20User%202.png)

---

## Summary & Key Takeaways
This lab provided hands-on experience deploying an enterprise identity infrastructure from scratch, from server promotion to client integration. By structuring nested Organizational Units, managing role-based Security Groups, and validating user authentication, I gained a practical understanding of centralized network administration. Additionally, diagnosing and remediating an accidental group assignment reinforced the critical importance of object auditing and real-world troubleshooting baselines.
