# Active Directory Configuration

## Overview

This section documents the Active Directory configuration completed in the lab.

The objective was to create a basic enterprise-style Active Directory environment that could be used to manage users, computers, security groups and access to resources from a central location.

---

## 1. Active Directory Domain

A Windows Server 2022 virtual machine was configured as the Domain Controller.

### Domain Configuration

| Setting           | Configuration       |
| ----------------- | ------------------- |
| Server Name       | `DC01`              |
| Operating System  | Windows Server 2022 |
| Domain            | `ReviveTech.local`  |
| Domain Controller | `DC01`              |
| Client Computer   | `PC01`              |

The domain provides centralized authentication and administration for the Windows client environment.

---

## 2. Organizational Units

Organizational Units (OUs) were created to organize users and computers within Active Directory.

The main `ReviveTech` OU was created with additional OUs underneath it for different groups of users and administrative functions.

Example structure:

```text
ReviveTech.local
│
└── ReviveTech
    │
    ├── IT SUPPORT
    │
    ├── USERS
    │
    └── IT ADMIN
```

Additional user and computer objects were placed into the appropriate OUs.

### Why OUs were used

OUs provide a structured way to organize Active Directory objects and make it easier to:

* Manage users and computers
* Apply Group Policy
* Delegate administration
* Separate departments or functions
* Maintain an organized directory

---

## 3. Creating Domain Users

Test user accounts were created to simulate employees within the organization.

Example users used during the lab included:

* John
* Sarah
* David
* Steve

These accounts were used to test authentication, permissions, Group Policy and helpdesk scenarios.

---

## 4. Security Groups

Security groups were created to manage access to resources.

Examples included:

```text
GG IT Support
GG Management
Domain Users
```

Users were added to the appropriate security groups based on their role.

For example:

```text
Steve
   │
   ├── Domain Users
   │
   └── GG IT Support
```

David was also used as a member of the management group:

```text
David
   │
   └── GG Management
```

### Why security groups were used

Security groups allow permissions to be assigned based on a user's role rather than configuring permissions individually for every user.

This makes access management easier to maintain as the organization grows.

---

## 5. Domain-Joining the Client

The Windows 11 client computer `PC01` was joined to the `ReviveTech.local` domain.

The process involved:

1. Configuring the network connection.
2. Confirming communication between `PC01` and `DC01`.
3. Configuring the appropriate DNS settings.
4. Verifying that the client could locate the Domain Controller.
5. Joining the computer to `ReviveTech.local`.
6. Restarting the client.
7. Logging in using a domain account.

The successful domain join allowed `PC01` to authenticate users against the Active Directory domain.

---

## 6. Active Directory Authentication

After joining `PC01` to the domain, domain accounts could be used to authenticate against the Domain Controller.

A domain login follows the format:

```text
REVIVETECH\username
```

For example:

```text
REVIVETECH\Administrator
```

This demonstrates centralized authentication through Active Directory.

---

## 7. Troubleshooting During Configuration

Several issues were encountered while building the lab.

### Network Connectivity

The client initially experienced connectivity problems because of incorrect IP addressing and network configuration.

The issue was investigated by checking:

* IP address
* Subnet mask
* Default gateway
* DNS configuration
* Connectivity to the gateway
* Connectivity to the Domain Controller

After correcting the network configuration, communication between the virtual machines was restored.

### DNS and Domain Join

DNS configuration was important because the Windows client needed to locate the Active Directory Domain Controller.

Connectivity and DNS settings were verified before attempting the domain join again.

### Time Synchronization

A time synchronization issue also affected domain authentication.

The client and Domain Controller were checked to ensure their system times were synchronized.

---

## 8. Skills Demonstrated

This section of the lab demonstrates practical experience with:

* Active Directory Domain Services
* Domain Controller administration
* Organizational Units
* User account management
* Security groups
* Domain authentication
* Domain joining
* Windows client administration
* DNS fundamentals
* IP addressing
* Network troubleshooting
* Access administration
* Basic enterprise Windows administration

---

## Outcome

The Active Directory environment was successfully configured with a Windows Server 2022 Domain Controller and Windows 11 domain client.

Users, Organizational Units and security groups were created and used to demonstrate centralized account and access management.

The environment was then used as the foundation for the Group Policy, permissions and helpdesk troubleshooting scenarios documented in the following sections.

