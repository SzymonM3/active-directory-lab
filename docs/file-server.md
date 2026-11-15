# File Server Configuration

## Overview

The lab uses the File Server role hosted on the Windows Server 2022 domain controller `LAB-DC01`.

The server provides an SMB network share for domain users.

## Shared Folder

| Parameter | Value |
|---|---|
| Share Name | `LabShare` |
| Local Path | `C:\LabShare` |
| Server | `LAB-DC01` |
| Access Protocol | SMB |

## SMB Share Permissions

The share permissions are configured as follows:

| Principal | Permission |
|---|---|
| `AD\Domain Users` | Read |
| `AD\GG_Ksiegowosc` | Change |

The custom security group `GG_Ksiegowosc` receives Change permissions at the share level.

## NTFS Permissions

The NTFS permissions on the root folder `C:\LabShare` include:

| Principal | Permission |
|---|---|
| `AD\Domain Users` | Read & Execute |
| `AD\GG_Ksiegowosc` | Modify |
| `SYSTEM` | Full Control |
| `Administrators` | Full Control |
| `BUILTIN\Users` | Read & Execute, Append Data, Create Files |

## Access Control Model

Access to files through the network share is controlled by both SMB share permissions and NTFS permissions.

The effective access level is determined by the combination of these two permission layers.

The `GG_Ksiegowosc` group has:

- Change permission at the SMB share level.
- Modify permission at the NTFS level.

The `Domain Users` group has:

- Read permission at the SMB share level.
- Read & Execute permission at the NTFS level.

## Current Scope

The current configuration documents one custom SMB share named `LabShare`.

The share is hosted on the domain controller and uses Active Directory security groups to manage access.

Further file server configuration and access-control scenarios may be documented as the lab develops.
