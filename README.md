# Active Directory Helpdesk Lab

## Project Overview

This repository documents a virtual IT infrastructure lab built with Oracle VirtualBox.

The environment consists of Windows Server 2022 and Windows 11 virtual machines configured to simulate a small domain-based network.

The lab is used to explore Windows Server administration, Active Directory Domain Services, DNS, network configuration, file sharing and access permissions.

The environment will be gradually extended with additional configurations and documented helpdesk incidents.

## Environment Architecture

The lab consists of two virtual machines connected through an isolated VirtualBox Internal Network.

| Virtual Machine | Operating System | Hostname | Role |
|---|---|---|---|
| WS2022-LAB | Windows Server 2022 Standard Evaluation | LAB-DC01 | Domain Controller, DNS, File Server |
| LAB-CLIENT01 | Windows 11 Pro | LAB-CLIENT01 | Domain Client |

### Domain Information

| Parameter | Value |
|---|---|
| Domain Name | ad.lab.test |
| NetBIOS Name | AD |
| Forest Functional Level | Windows Server 2016 |
| Domain Functional Level | Windows Server 2016 |
| Domain Controller | LAB-DC01.ad.lab.test |

## Network Configuration

Both virtual machines use the VirtualBox Internal Network named `IT-LAB`.

| Parameter | LAB-DC01 | LAB-CLIENT01 |
|---|---|---|
| IPv4 Address | 192.168.50.10 | 192.168.50.20 |
| Subnet Mask | 255.255.255.0 | 255.255.255.0 |
| DNS Server | 127.0.0.1 | 192.168.50.10 |
| Default Gateway | Not configured | Not configured |

Both machines are configured with IPv4 addresses within the same /24 subnet.

## Infrastructure Components

### Active Directory Domain Services

- Domain: `ad.lab.test`
- Domain Controller: `LAB-DC01`
- Organizational Unit: `Domain Controllers`
- User accounts managed through Active Directory
- Custom security group: `GG_Ksiegowosc`

### DNS

The domain controller hosts Active Directory-integrated DNS zones, including:

- `ad.lab.test`
- `_msdcs.ad.lab.test`

Root Hints are enabled. No manual DNS forwarder addresses are configured.

### File Services

The server provides an SMB network share:

| Share Name | Local Path |
|---|---|
| LabShare | C:\LabShare |

Access is controlled through SMB share permissions and NTFS permissions.

The custom security group `GG_Ksiegowosc` has Change permissions at the share level and Modify permissions at the NTFS level.

## Virtual Machine Resources

| Resource | WS2022-LAB | LAB-CLIENT01 |
|---|---|---|
| RAM | 4 GB | 4 GB |
| Virtual CPUs | 2 | 2 |
| Firmware | UEFI | UEFI |
| TPM | Not configured | TPM 2.0 |
| Secure Boot | Disabled | Enabled |
| Network Adapter | Intel PRO/1000 MT Desktop | Intel PRO/1000 MT Desktop |

## Repository Structure

```text
active-directory-lab/
├── README.md
├── docs/
├── diagrams/
├── screenshots/
│   ├── virtualbox/
│   ├── server/
│   └── client/
└── incidents/
```

### Documentation

The `docs/` directory contains technical documentation describing the lab infrastructure and its configuration.

### Diagrams

The `diagrams/` directory contains infrastructure and network topology diagrams.

### Screenshots

The `screenshots/` directory contains selected screenshots documenting the virtual machines and their configuration.

### Incidents

The `incidents/` directory is reserved for documented helpdesk incidents and troubleshooting scenarios.

Additional incidents will be added as the lab develops.

## Project Status

**Status: In Progress**

The basic domain environment has been configured. Further development will include additional Windows Server administration tasks, infrastructure configuration and documented helpdesk scenarios.

