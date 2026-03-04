Active Directory Simulation – SolaraIA Tech
📌 Project Overview

This project demonstrates the deployment and configuration of a Windows Server Domain Controller (Active Directory) for a simulated multi-branch enterprise called SolaraIA Tech.

The lab simulates centralized identity and access management across multiple locations using Windows Server 2022 and Active Directory Domain Services (AD DS).

🔧 Implementation Includes

Domain Controller deployment

DNS configuration

Multi-location Organizational Unit (OU) design

User and security group creation

Group Policy Object (GPO) enforcement

Enterprise security hardening

Policy validation and testing

🏢 Company Structure
Chicago (Headquarters)

Finance Department

IT Department

Indiana Location

Tax Department

Treasury Department

Wisconsin Location

Audit Department

HR Department

🎯 Project Objectives

Deploy Windows Server 2022 as a Domain Controller

Configure AD DS

Design structured OUs

Implement RBAC

Enforce password & lockout policies

Restrict CMD, PowerShell, Control Panel

Configure DNS

Validate policies using:

gpupdate /force
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
⚙️ IP Configuration

Domain Name: SolaraIA.com

Server Name: SolaraIA

Server IP: 10.0.5.4

Gateway: 10.0.5.1

🧩 Domain Configuration

Installed AD DS

Promoted to Domain Controller

Created domain: SolaraIA.com

Configured DNS

Verified login:

SolaraIA\Administrator
🗂️ OU Design
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
👥 Users & Groups

Created department security groups

Created user accounts

Assigned users to groups

Applied RBAC

🔐 Group Policy (GPO)
Password Policy

Complexity enabled

Minimum length enforced

Account Lockout

3 failed attempts

System Restrictions

Disabled CMD

Blocked PowerShell

Restricted Control Panel

Deployment

Linked GPOs to OUs

Applied with:

gpupdate /force
📸 Screenshots
/screenshots
screenshots.md
✅ Key Takeaways

Built a multi-branch AD environment

Designed scalable OU structure

Implemented enterprise security policies

Centralized access management

Validated GPO enforcement

🛠️ Skills Demonstrated

Active Directory

Windows Server 2022

DNS

OU Design

GPO Management

RBAC

Security Hardening

Networking
