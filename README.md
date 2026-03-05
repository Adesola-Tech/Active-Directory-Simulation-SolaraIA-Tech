# Active Directory Simulation – SolaraIA Tech
###
📌 Project Overview
##
This project demonstrates the deployment and configuration of a Windows Server Domain Controller (Active Directory) for a simulated multi-branch enterprise called SolaraIA Tech.

The lab simulates centralized identity and access management across multiple locations using Windows Server 2022 and Active Directory Domain Services (AD DS).
##
The window implementation Includes

- Domain Controller deployment

- DNS configuration

- Multi-location Organizational Unit (OU) design

- User and security group creation

- Group Policy Object (GPO) enforcement

- Enterprise security hardening

- Policy validation and testing
##
Company Structure
---
Chicago (Headquarters)

- Finance Department

- IT Department

Indiana Location

- Tax Department

- Treasury Department

Wisconsin Location

- Audit Department

- HR Department

All branches are centrally managed using Active Directory to enforce security policies, manage users, and control access across the organization. 
##
Project Objectives

The objectives of this simulation were to: 

- Deploy Windows Server 2022 as a Domain Controller
- Configure Active Directory Domain Services (AD DS)
- Design structured OUs based on location and department
- Implement role-based access control using security groups
- Enforce password and account lockout policies
- Restrict system-level tools (CMD, PowerShell, Control Panel)
- Configure DNS for domain communication
- Validate policy enforcement using ```gpupdate /force```

🌐 Network Design
```
🌐 Internet
│
┌────────────────┐
│ Router         │
│ Gateway:       │
│ 10.0.5.1       │
└────────────────┘
│
┌────────────────┐
│ Switch         │
└────────────────┘
│
├───────────────────────┬────────────────────────┐
│                       │                        │
┌────────────────┐  ┌────────────────┐   ┌────────────────┐
│ SolaraIA       │  │ Client PC 1    │   │ Client PC 2    │
│ (Domain Ctrl)  │  │ Wisconsin User │   │ Chicago User   │
│ 10.0.5.4       │  │                │   │                │
└────────────────┘  └────────────────┘   └────────────────┘
│
┌────────────────┐
│ Client PC 3    │
│ Indiana User   │
└────────────────┘
```
##
IP Configuration
---
- Domain Name: SolaraIA.com

- Server Name: SolaraIA

- Server IP: 10.0.5.4

- Gateway: 10.0.5.1

All client machines were configured to use the Domain Controller as their primary DNS server to enable domain authentication. 
###
Domain Configuration
---
- Installed Active Directory Domain Services (AD DS)

- Promoted to Domain Controller

- Created domain: SolaraIA.com

- Configured DNS services

- Verified domain login using ```SolaraIA\Administrator```
##
Organizational Unit (OU) Design
---
```
SolaraIA.com
│
├── Wisconsin
│   ├── Audit
│   └── HR
│
├── Chicago
│   ├── Finance
│   └── IT
│
└── Indiana
    ├── Tax
    └── Treasury
```

This structure allows: 

- Targeted GPO enforcement
  
- Department-level access control
  
- Administrative delegation
  
- Scalable enterprise design
##
Users & Security Groups
---
For each department: 

- Security groups were created
- Individual user accounts were created
- Users were assigned to department-specific groups
- Access control was applied using group membership

This follows a role-based access control (RBAC) model.
##
Group Policy Objects (GPO)
---
The following security policies were implemented: 

Password Policy
---
- Enforced password complexity

- Minimum password length requirement

Account Lockout Policy
---
- Lockout threshold: 3 failed login attempts

- Mitigates brute-force attacks

System Restrictions
---
- Disabled Command Prompt

- Blocked PowerShell access

- Restricted Control Panel access

Deployment
---
- GPOs linked to appropriate Organizational Units

- Policies applied using ```gpupdate /force```
  
- Enforcement validated on client systems
##
Screenshots
---

Screenshots documenting the full implementation process are available in: 
- ```screenshots/``` folder
- ```screenshots.md``` file

  - Screenshots
##
Key implementation stages captured: 
---
- VM grouping

- AD DS installation

- Domain Controller promotion

- OU structure creation

- User & group creation

- DNS configuration

- GPO linking

- Policy enforcement validation  
##
Key Takeaways
---
- Successfully deployed and configured a multi-branch Active Directory environment

- Implemented structured OU design based on geography and department

- Implemented enterprise-level security hardening policies

- Demonstrated centralized identity and access management

- Validated policy enforcement in a simulated corporate environment
##
Skills Demonstrated
---
- Active Directory Administration

- Windows Server 2022

- DNS Configuration

- Organization Unit Design

- Group Policy Object (GPO) Management

- Role-Based Access Control (RBAC)

- Enterprise Security Hardening

- Networking configuration
