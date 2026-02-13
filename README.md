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

---

### 4. Client Machine Setup

A separate client virtual machine was deployed and configured to join the domain.

Steps included:

- Deploying a Windows client VM
- Configuring DNS to point to the domain controller
- Joining the computer to the domain
- Logging in with domain user credentials

Successful login confirmed proper domain communication.

---

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

## Screenshots

(Add your screenshots below this section)



