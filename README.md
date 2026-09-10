# Active Directory IT Support Lab

## Overview

This project is a hands-on Active Directory and IT Support home lab built to simulate a small enterprise Windows environment.

The lab focuses on practical IT support and system administration tasks, including Active Directory user administration, security groups, Group Policy, file and folder permissions, domain-joined computers, and troubleshooting common user access issues.

The project also includes realistic helpdesk scenarios that demonstrate the troubleshooting process from identifying a problem through to implementing and verifying a resolution.

---

## Objectives

The main objectives of this lab are to:

* Build and configure a Windows Server Active Directory environment
* Configure a Domain Controller
* Configure networking and DNS
* Create and manage Organizational Units (OUs)
* Create and manage domain users
* Create and manage security groups
* Join a Windows client computer to the domain
* Configure and test Group Policy
* Implement file and folder permissions
* Troubleshoot account and access problems
* Simulate real-world IT support tickets
* Document troubleshooting steps and resolutions

---

## Lab Environment

| Component         | Configuration       |
| ----------------- | ------------------- |
| Virtualization    | VMware              |
| Domain Controller | Windows Server 2022 |
| Client Computer   | Windows 11          |
| Domain            | `ReviveTech.local`  |
| Domain Controller | `DC01`              |
| Client            | `PC01`              |
| Network           | `192.168.134.0/24`  |
| DC01 IP           | `192.168.134.10`    |
| PC01 IP           | `192.168.134.129`   |

---

## Technologies and Tools

* Windows Server 2022
* Windows 11
* Active Directory Domain Services (AD DS)
* DNS
* Group Policy
* Windows File and Folder Permissions
* VMware
* Command Prompt
* PowerShell
* Remote troubleshooting concepts
* IT Service Desk / Helpdesk processes

---

## Active Directory Structure

The lab uses the `ReviveTech.local` Active Directory domain.

The environment includes:

* Organizational Units
* Domain Users
* IT Support users
* Management users
* Security groups
* Domain-joined client computers

The Active Directory structure was designed to demonstrate how users, computers and permissions can be organised in a manageable enterprise environment.

---

## Group Policy

Group Policy was used to demonstrate centralized management of Windows security and user settings.

Examples covered in this lab include:

* Password security policies
* Account lockout policies
* Logon security policies
* Testing policy application
* Troubleshooting Group Policy issues

---

## File and Folder Permissions

The lab includes practical file access scenarios designed to demonstrate Windows security permissions and group-based access control.

Examples include:

* HR folder access
* Domain Users permissions
* Security group permissions
* IT Support elevated access
* Troubleshooting `Access Denied` errors

Permissions were configured using security groups rather than assigning access individually wherever possible.

---

## Helpdesk Troubleshooting Scenarios

The lab includes realistic IT support tickets based on common enterprise support issues.

### Example Tickets

| Ticket | Issue                               | Skills Demonstrated             |
| ------ | ----------------------------------- | ------------------------------- |
| 001    | User unable to log in               | Account troubleshooting         |
| 002    | User account locked out             | Account lockout troubleshooting |
| 003    | User cannot access HR folder        | NTFS/share permissions          |
| 004    | IT Support requires elevated access | Security groups and permissions |
| 005    | Group Policy troubleshooting        | GPO and policy verification     |

Each ticket documents:

1. Reported problem
2. Initial investigation
3. Troubleshooting steps
4. Root cause
5. Resolution
6. Verification

---

## Documentation

Detailed documentation for the lab is available in the `documentation` directory.

```text
documentation/
├── 01-lab-environment.md
├── 02-active-directory.md
├── 03-group-policy.md
├── 04-file-permissions.md
└── 05-helpdesk-tickets.md
```

---

## Screenshots

Screenshots are included to provide evidence of the configurations and troubleshooting performed during the lab.

```text
screenshots/
├── ad-users-groups/
├── group-policy/
├── permissions/
└── ticket-resolution/
```

---

## Skills Demonstrated

This project demonstrates practical experience with:

* Active Directory administration
* User account administration
* Security group management
* Organizational Unit management
* Group Policy
* Windows security
* File and folder permissions
* Basic DNS and networking
* Windows troubleshooting
* Helpdesk incident investigation
* Access administration
* Technical documentation
* Problem solving

---

## What I Learned

Building this lab helped me develop a better understanding of how enterprise Windows environments are structured and supported.

Rather than only configuring the environment, I used realistic support scenarios to practise investigating problems, identifying root causes, applying appropriate fixes, and verifying that the issue was resolved.

The lab also helped strengthen my understanding of the relationship between Active Directory users, security groups, Group Policy and Windows permissions.

---

## Future Improvements

Planned improvements to the lab include:

* Adding additional Windows client machines
* Expanding the Active Directory structure
* Implementing additional Group Policies
* Adding more helpdesk scenarios
* Adding PowerShell administration tasks
* Expanding the network environment
* Integrating the lab with a dedicated firewall/networking lab
* Adding monitoring and logging scenarios

---

## Project Structure

```text
active-directory-it-support-lab/
│
├── README.md
│
├── documentation/
│   ├── 01-lab-environment.md
│   ├── 02-active-directory.md
│   ├── 03-group-policy.md
│   ├── 04-file-permissions.md
│   └── 05-helpdesk-tickets.md
│
├── screenshots/
│   ├── ad-users-groups/
│   ├── group-policy/
│   ├── permissions/
│   └── ticket-resolution/
│
└── diagrams/
    └── network-topology.png
```

---

## Disclaimer

This is a personal educational home lab created for learning, practice and portfolio purposes. The environment is not connected to any production network or organisation.
