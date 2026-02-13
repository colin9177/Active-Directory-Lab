# Active Directory Home Lab – Jake’s Tech Lab

## Project Overview

This project documents the creation of a Windows Active Directory home lab environment using Microsoft Azure. The purpose of this lab was to simulate a small business network and gain hands-on experience with domain controllers, user authentication, and centralized network management.

The lab demonstrates practical skills in system administration, virtualization, networking, and troubleshooting within an enterprise-style environment.

---

## Objectives

The primary objectives of this lab were:

- Deploy a Windows Server virtual machine to act as a domain controller
- Install and configure Active Directory Domain Services (AD DS)
- Create and manage domain users and groups
- Join a client computer to the domain
- Configure networking to support domain communication
- Practice troubleshooting login and connectivity issues

---

## Tools & Technologies Used

- Microsoft Azure Virtual Machines
- Windows Server (Domain Controller)
- Windows Client OS
- Active Directory Domain Services (AD DS)
- Remote Desktop Protocol (RDP)
- DNS Configuration
- Virtual Networking

---

## Lab Environment Setup

### 1. Virtual Network Configuration

A virtual network was created in Azure to simulate an internal business network. This allowed communication between the domain controller and client machine.

Key setup steps included:

- Creating a virtual network and subnet
- Assigning private IP addresses
- Ensuring both machines were on the same network

This network structure mimics how internal corporate networks operate.

---

### 2. Domain Controller Deployment

A Windows Server virtual machine was deployed to serve as the domain controller.

Steps performed:

- Created a Windows Server VM in Azure
- Configured networking settings
- Connected via Remote Desktop
- Installed Active Directory Domain Services
- Promoted the server to a domain controller
- Created a new domain forest

This server became responsible for centralized authentication and directory services.

---

### 3. Active Directory Configuration

After installing AD DS, several administrative tasks were completed:

- Created organizational units (OUs)
- Added test user accounts
- Configured user permissions
- Verified domain functionality

This simulates real-world user and access management in enterprise environments.

<img width="966" height="1080" alt="Screenshot (57)" src="https://github.com/user-attachments/assets/e5f1f753-85e6-4974-9569-f70f4aa05cb0" />
<img width="960" height="1080" alt="Screenshot (58)" src="https://github.com/user-attachments/assets/8c1573aa-77b3-467f-a643-f242f4a3cad9" />
<img width="967" height="1080" alt="Screenshot (59)" src="https://github.com/user-attachments/assets/c8b7494c-706b-4902-b8b3-f9c448ad51c7" />

### 4. Client Machine Setup

A separate client virtual machine was deployed and configured to join the domain.

Steps included:

- Deploying a Windows client VM
- Configuring DNS to point to the domain controller
- Joining the computer to the domain
- Logging in with domain user credentials

Successful login confirmed proper domain communication.
<img width="961" height="1080" alt="Screenshot (60)" src="https://github.com/user-attachments/assets/fea8fd0f-df09-44f4-8d14-e801e86fca92" />
<img width="969" height="1080" alt="Screenshot (61)" src="https://github.com/user-attachments/assets/2f79a32f-61c7-4b3e-ab05-ed1c8eaa7883" />
<img width="1920" height="1080" alt="Screenshot (62)" src="https://github.com/user-attachments/assets/4992b038-4923-4d41-9d70-4140ff26e16f" />
<img width="1920" height="1080" alt="Screenshot (63)" src="https://github.com/user-attachments/assets/f4f161c7-bd8d-4e74-b5ab-62dcda3bc71f" />
<img width="1920" height="1080" alt="Screenshot (64)" src="https://github.com/user-attachments/assets/4e4da684-3968-4fec-b69c-3ff5020fd886" />

---

## Advanced Active Directory Configuration

This section documents additional administrative tasks performed to simulate real-world enterprise Active Directory management. These exercises focused on security policy enforcement, automation, delegation of permissions, and organizational structure.

---

### 1. Domain Password Policy Configuration

Password policies are enforced at the domain level using Group Policy to maintain security standards across all users.

For this lab, the Default Domain Policy was edited for educational purposes. In production environments, organizations often use more advanced or fine-grained password policies.

Steps performed:

- Opened **Group Policy Management**
- Expanded: Forest → Domains → lab.local
- Edited the **Default Domain Policy**
- Navigated to:

  Computer Configuration  
  → Policies  
  → Windows Settings  
  → Security Settings  
  → Account Policies  
  → Password Policy

- Configured key security settings including:
  - Maximum password age
  - Minimum password length

This exercise demonstrated how centralized security policies are enforced domain-wide.

---

### 2. Logon Script Implementation

Logon scripts automate actions when users sign in. They are commonly used to configure environments, display messages, or map network resources.

A basic logon script was created to demonstrate automated user interaction.

Steps performed:

- Created a text file named **logon.bat**
- Added the following command:

  `echo Welcome to the domain`

- Saved the file to the SYSVOL scripts directory:

  `C:\Windows\SYSVOL\sysvol\lab.local\scripts`

SYSVOL is a shared domain controller folder that stores files required by all domain users, including Group Policy objects and scripts.

The script was assigned to a user account through:

- Active Directory Users and Computers
- User Properties → Profile tab
- Entered **logon.bat** in the Logon Script field

This confirmed that user logon automation was functioning correctly.

---

### 3. Delegating Password Reset Permissions

Permission delegation allows non-administrative staff to perform limited management tasks. This mirrors real-world helpdesk workflows.

Steps performed:

- Right-clicked the Users Organizational Unit  
  (_Branches → Houston → Users)
- Selected **Delegate Control**
- Added the **Helpdesk** security group
- Assigned permissions to:
  - Reset user passwords
  - Force password change at next logon

This demonstrated role-based access control and secure delegation practices.

---

### 4. Organizing Computer Objects into Branch OUs

By default, newly joined domain computers are placed in a generic container. For proper management and policy application, systems must be organized into appropriate Organizational Units.

Steps performed:

- Opened Active Directory Users and Computers
- Located the client machine (e.g., CLIENT01)
- Moved the computer object to:

  _Branches → Houston → Workstations

This ensured the device received the correct Group Policy settings and organizational structure.


<img width="967" height="1080" alt="Screenshot (65)" src="https://github.com/user-attachments/assets/77353d35-0401-44b0-a749-1ede0aa8d5c7" />
<img width="969" height="1080" alt="Screenshot (66)" src="https://github.com/user-attachments/assets/ffbdcdcd-5f00-43a9-9914-cb7b7634d288" />
<img width="960" height="1080" alt="Screenshot (67)" src="https://github.com/user-attachments/assets/9cf2ab7b-7545-4f19-8b50-9e9656d1f48f" />
<img width="960" height="1080" alt="Screenshot (68)" src="https://github.com/user-attachments/assets/2b5f7f03-1c7c-4057-a270-7e2fb4198317" />
<img width="961" height="1080" alt="Screenshot (69)" src="https://github.com/user-attachments/assets/9dc7d6e2-2353-4ced-a15c-6bd94d42608d" />
<img width="955" height="1080" alt="Screenshot (70)" src="https://github.com/user-attachments/assets/0f30f41b-f17f-4dff-b942-3d61812b0ea8" />


## Challenges Encountered

During the lab, several issues required troubleshooting:

- DNS misconfiguration preventing domain joining
- Network communication delays
- Authentication errors during login

These problems were resolved by reviewing network settings, verifying DNS configuration, and restarting services when necessary.

This troubleshooting process reinforced the importance of correct network configuration in Active Directory environments.

---

## Results

The lab successfully created a functioning Active Directory domain environment.

Key outcomes:

- Domain controller fully operational
- Users able to authenticate through Active Directory
- Client machine successfully joined to the domain
- Network communication functioning properly

This environment replicates a simplified enterprise IT infrastructure.

---

## Skills Demonstrated

This project demonstrates practical experience in:

- Windows Server administration
- Active Directory configuration
- Virtual networking
- System deployment in cloud environments
- Troubleshooting authentication and network issues
- Documentation and technical communication

---

## What I Learned

This lab provided hands-on understanding of how Active Directory manages centralized authentication and user administration. It reinforced the importance of DNS configuration, network planning, and systematic troubleshooting.

The project also improved my confidence working with enterprise-style infrastructure and cloud-based virtual machines.

---





