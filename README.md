# Active Directory & IT Support Home Lab

A hands-on Windows Server and Active Directory lab built in VMware Workstation to simulate a small business IT environment and practise real-world IT Support and System Administration scenarios.

## Project Overview

The lab environment, **ReviveTech**, includes a Windows Server 2022 Domain Controller and Windows 11 workstation.

The project focuses on building, securing and troubleshooting a Windows domain environment rather than simply documenting installation steps.

## Environment

| Component         | Configuration                    |
| ----------------- | -------------------------------- |
| Hypervisor        | VMware Workstation Pro           |
| Server            | Windows Server 2022              |
| Client            | Windows 11                       |
| Domain Controller | DC01                             |
| Workstation       | PC01                              |
| Domain            | ReviveTech.local                 |
| Directory Service | Active Directory Domain Services |
| DNS               | Windows Server DNS               |
| Network           | VMware NAT / IPv4                |

## Active Directory

Created and organised:

* Users
* Organisational Units
* Security Groups
* Computer OUs
* Department-based access control
* IT Support administration structure

### Security Groups

* `GG_ITAdmins`
* `GG_ITSupport`
* `GG_HR`
* `GG_Finance`
* `GG_Management`

## Group Policy

Created:

`GPO_Workstation_Baseline`

Configured and tested:

* Interactive logon notification
* 15-minute workstation inactivity policy
* Password policy
* Account lockout policy

Used:

```text
gpupdate /force
gpresult /scope computer /r
gpresult /scope computer /v
```

to troubleshoot and verify policy application.

## Helpdesk Scenarios

### 1. GPO Not Applying

**Issue:** Workstation was not receiving the expected security policy.

**Investigation:** Checked OU placement, GPO linking and applied policies.

**Root Cause:** Workstation had been moved out of the OU containing the GPO link.

**Resolution:** Returned the workstation to the correct OU and verified the policy with `gpresult`.

---

### 2. Shared Folder Access Denied

**Issue:** Management user could not access the Management share.

**Investigation:** Checked Active Directory group membership before changing permissions.

**Root Cause:** User had been removed from `GG_Management`.

**Resolution:** Restored group membership and verified access after re-authentication.

---

### 3. Account Lockout

**Issue:** Finance user could not log in.

**Investigation:** Checked the user's AD account properties.

**Root Cause:** Account was locked.

**Resolution:** Unlocked the account and verified successful authentication.

---

### 4. Password Reset

Practised:

* Administrator-assisted password reset
* Temporary passwords
* Force password change at next logon
* Verification of successful authentication

---

### 5. User Onboarding & Offboarding

Practised:

* Creating new users
* Assigning department security groups
* Testing access
* Disabling accounts during offboarding
* Verifying that disabled accounts could no longer authenticate

## Permissions

Created department shared folders and configured access using:

* Share permissions
* NTFS permissions
* Security groups

Example:

```text
User
  ↓
GG_Management
  ↓
Management Share
```

This demonstrates group-based access control instead of assigning permissions individually to users.

## Delegated Administration

Configured delegated permissions for the IT Support security group to perform selected user-management tasks without making support staff Domain Administrators.

This demonstrates the principle of **least privilege**.

## Troubleshooting Tools

Tools used throughout the lab included:

```text
ipconfig
ping
nslookup
nltest
gpupdate
gpresult
```

along with:

* Active Directory Users and Computers
* Group Policy Management
* Windows Event/administrative tools
* Windows network configuration tools

## Skills Demonstrated

**Active Directory**

* AD DS
* Users and Groups
* OUs
* Security Groups
* Account Management
* Delegation

**Group Policy**

* GPO creation
* GPO linking
* Policy configuration
* Policy troubleshooting
* Policy verification

**Networking**

* IPv4
* DNS
* Default gateways
* Domain connectivity
* DNS troubleshooting

**IT Support**

* Ticket investigation
* Root-cause analysis
* User access troubleshooting
* Password resets
* Account lockouts
* Onboarding/offboarding
* Access control

## Project Approach

Each scenario followed a basic IT Support workflow:

**Ticket → Investigation → Root Cause → Resolution → Verification → Documentation**

## Future Improvements

Planned additions include:

* Additional Windows clients
* DHCP
* File server structure
* Printer management
* More Group Policy scenarios
* Windows Server administration
* PowerShell automation
* Microsoft Entra ID / Azure integration
* Endpoint management scenarios
