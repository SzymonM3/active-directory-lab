# Active Directory Configuration

## Domain Overview

The lab uses an Active Directory Domain Services environment hosted on Windows Server 2022.

| Parameter | Value |
|---|---|
| Domain DNS Name | ad.lab.test |
| NetBIOS Name | AD |
| Domain Controller | LAB-DC01.ad.lab.test |
| Domain Functional Level | Windows Server 2016 |
| Forest Functional Level | Windows Server 2016 |

## Domain Controller

The domain controller is running on the `LAB-DC01` virtual machine.

Installed server roles relevant to the domain environment:

- Active Directory Domain Services (AD DS)
- DNS Server

All five Flexible Single Master Operations (FSMO) roles are assigned to `LAB-DC01.ad.lab.test`:

| FSMO Role | Assigned Server |
|---|---|
| Schema Master | LAB-DC01.ad.lab.test |
| Domain Naming Master | LAB-DC01.ad.lab.test |
| PDC Emulator | LAB-DC01.ad.lab.test |
| RID Master | LAB-DC01.ad.lab.test |
| Infrastructure Master | LAB-DC01.ad.lab.test |

## Active Directory Structure

The current domain structure includes the following organizational unit:

| Organizational Unit | Distinguished Name |
|---|---|
| Domain Controllers | OU=Domain Controllers,DC=ad,DC=lab,DC=test |

User accounts are stored in the default `Users` container.

### User Accounts

| Account | Status | Description |
|---|---|---|
| Administrator | Enabled | Built-in administrative account |
| Guest | Disabled | Built-in guest account |
| krbtgt | Disabled | Built-in Kerberos account |
| jan.kowalski | Enabled | Lab user account |

### Security Groups

The lab includes a custom global security group:

| Parameter | Value |
|---|---|
| Group Name | GG_Ksiegowosc |
| Group Scope | Global |
| Group Category | Security |
| Member | jan.kowalski |

The `jan.kowalski` account is also a member of the default `Domain Users` group.

## Domain Functional Configuration

- The domain and forest functional levels are set to Windows Server 2016.
- The domain controller hosts all five FSMO roles.
- Active Directory-integrated DNS is used for domain name resolution.

## Current Scope

The current environment contains one domain controller and one domain-joined Windows client.

There are no additional domain controllers or custom organizational units documented in the current configuration.

Further Active Directory configuration and administration scenarios may be added as the lab develops.
