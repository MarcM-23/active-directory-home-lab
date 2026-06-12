# Windows Server + Active Directory Home Lab

## Overview

This project documents a Windows Server and Active Directory home lab built using Hyper-V. The goal of this lab was to gain hands-on experience with common IT Help Desk and desktop support tasks, including domain setup, DNS configuration, domain-joined client management, user account administration, password resets, group membership, and organizational unit management.

The lab simulates a small business environment with a Windows Server domain controller and a Windows 11 client workstation joined to the domain.

## Lab Environment

| Component               | Details                      |
| ----------------------- | ---------------------------- |
| Virtualization Platform | Hyper-V                      |
| Server                  | Windows Server 2022          |
| Client                  | Windows 11                   |
| Domain                  | marclab.local                |
| Domain Controller       | Server01                     |
| Client Workstation      | Client01                     |
| Network Type            | Internal Hyper-V lab network |

## Lab Topology

```text
Hyper-V Host
│
├── Server01
│   ├── Windows Server 2022
│   ├── Active Directory Domain Services
│   ├── DNS Server
│   └── Domain Controller for marclab.local
│
└── Client01
    ├── Windows 11
    └── Domain-joined workstation
```

## Objectives

The main objectives of this lab were to:

* Build a Windows Server virtual machine in Hyper-V
* Configure a static IP address for the server
* Install Active Directory Domain Services
* Promote the server to a domain controller
* Create the `marclab.local` domain
* Configure DNS for domain communication
* Create and organize users, computers, groups, and OUs
* Join a Windows 11 client to the domain
* Practice common help desk account management tasks
* Document troubleshooting steps and mock support tickets

## Skills Demonstrated

This lab demonstrates hands-on experience with:

* Windows Server administration
* Active Directory Users and Computers
* Domain controller configuration
* DNS troubleshooting
* Windows 11 domain joining
* User account creation
* Password resets
* Account unlocks
* Account disabling and enabling
* Security group creation
* Group membership management
* Organizational Unit management
* Basic help desk documentation
* Hyper-V virtual machine management

## Active Directory Structure

The lab included the creation and organization of several Active Directory objects.

Example structure:

```text
marclab.local
│
├── Departments
│   ├── HR
│   ├── IT
│   └── Finance
│
├── Lab Computers
│   └── Client01
│
├── Lab Groups
│   ├── HR_Users
│   ├── Finance_Users
│   ├── IT_Support
│   ├── Password_Reset_Team
│   └── Shared_Drive_Users
│
├── Lab Users
│
└── Disabled Users
```

## Tasks Completed

### 1. Windows Server Setup

Created a Windows Server virtual machine in Hyper-V and installed Windows Server 2022 with Desktop Experience.

### 2. Network Configuration

Configured the server with a static IP address and set the DNS server to point to the domain controller.

Example server configuration:

```text
Server: Server01
IP Address: 192.168.50.10
Subnet Mask: 255.255.255.0
DNS Server: 192.168.50.10
```

### 3. Active Directory Installation

Installed Active Directory Domain Services and promoted the server to a domain controller for the domain:

```text
marclab.local
```

### 4. Windows 11 Client Domain Join

Created a Windows 11 virtual machine named `Client01`, configured its DNS settings, verified communication with the domain controller, and joined it to the `marclab.local` domain.

Example client configuration:

```text
Client: Client01
IP Address: 192.168.50.20
DNS Server: 192.168.50.10
Domain: marclab.local
```

### 5. DNS and Connectivity Testing

Verified network and DNS communication using commands such as:

```cmd
ping 192.168.50.10
ping Server01
nslookup marclab.local
ipconfig /all
```

### 6. User and Group Management

Created users, organizational units, and security groups. Practiced assigning users to groups based on department and job function.

Example users:

```text
tuser
hdesk
jrivera
```

Example groups:

```text
HR_Users
IT_Support
Finance_Users
Password_Reset_Team
Shared_Drive_Users
```

### 7. Password Reset Practice

Practiced resetting a domain user password using Active Directory Users and Computers. The user was assigned a temporary password and required to change it at the next logon.

### 8. Account Lockout and Unlock Practice

Configured and tested account lockout behavior by entering an incorrect password multiple times. Practiced unlocking the account from Active Directory Users and Computers.

### 9. Account Disable and Enable Practice

Disabled a user account to simulate an offboarding or security-related help desk request. Then re-enabled the account and verified that the user could log in again.

### 10. Help Desk Ticket Documentation

Created mock help desk tickets to document common support scenarios, including password resets, account lockouts, and new employee onboarding.

## Example Help Desk Tickets

### Ticket 001: Password Reset

**Issue:**
User could not log in and requested a password reset.

**Troubleshooting Steps:**
Verified the user account in Active Directory Users and Computers. Reset the password to a temporary password and selected the option requiring the user to change the password at next logon.

**Resolution:**
User successfully logged into the domain using the temporary password and created a new password.

**Status:**
Resolved

---

### Ticket 002: Account Locked

**Issue:**
User account was locked after multiple failed login attempts.

**Troubleshooting Steps:**
Opened Active Directory Users and Computers, located the user account, checked the account status, and unlocked the account.

**Resolution:**
User account was unlocked and access was restored.

**Status:**
Resolved

---

### Ticket 003: New Employee Onboarding

**Issue:**
New employee needed a domain account.

**Troubleshooting Steps:**
Created a new domain user, assigned a temporary password, required password change at next logon, and added the user to the appropriate security groups.

**Resolution:**
New employee account was created and verified through a successful domain login.

**Status:**
Resolved

## Screenshots

Screenshots from the lab are included in the project documentation PDF.

Recommended folder structure:

```text
active-directory-home-lab
│
├── README.md
├── Windows_Server_Active_Directory_Home_Lab.pdf
├── screenshots
│   ├── server-setup.png
│   ├── active-directory-users-computers.png
│   ├── dns-testing.png
│   ├── domain-join.png
│   └── password-reset.png
│
└── tickets
    └── help-desk-ticket-examples.txt
```

## Documentation

A full PDF version of the lab documentation is included in this repository.

**PDF:** `Windows_Server_Active_Directory_Home_Lab.pdf`

## Summary

This lab provided hands-on experience with Windows Server, Active Directory, DNS, Hyper-V, and Windows domain administration. It also helped reinforce common IT Help Desk responsibilities such as resetting passwords, unlocking accounts, creating users, managing groups, organizing OUs, troubleshooting domain connectivity, and documenting support tickets.

This project was completed as part of my continued preparation for IT Help Desk, Desktop Support, and Technical Support roles.
