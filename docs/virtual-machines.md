
# Virtual Machine Configuration

## Overview

The lab environment consists of two virtual machines running in Oracle VirtualBox.

Both machines use UEFI firmware and an Intel PRO/1000 MT Desktop virtual network adapter. They are connected to the same VirtualBox Internal Network named `IT-LAB`.

## Windows Server 2022 — LAB-DC01

| Parameter | Configuration |
|---|---|
| VirtualBox VM Name | `WS2022-LAB` |
| Operating System | Windows Server 2022 Standard Evaluation |
| Hostname | `LAB-DC01` |
| Memory (RAM) | 4096 MB |
| Virtual CPUs | 2 |
| Chipset | PIIX3 |
| Firmware | UEFI |
| Secure Boot | Disabled |
| TPM | Not configured |
| Network Adapter | Intel PRO/1000 MT Desktop |
| Network Attachment | Internal Network |
| Internal Network Name | `IT-LAB` |
| IPv4 Address | `192.168.50.10/24` |

### Server Roles

The virtual machine hosts the following infrastructure services:

- Active Directory Domain Services (AD DS)
- DNS Server
- File Server

## Windows 11 — LAB-CLIENT01

| Parameter | Configuration |
|---|---|
| VirtualBox VM Name | `LAB-CLIENT01` |
| Operating System | Windows 11 Pro |
| Version | 26H2 |
| OS Build | 26300.9711 |
| Hostname | `LAB-CLIENT01` |
| Memory (RAM) | 4096 MB |
| Virtual CPUs | 2 |
| Chipset | PIIX3 |
| Firmware | UEFI |
| Secure Boot | Enabled |
| TPM | TPM 2.0 |
| Network Adapter | Intel PRO/1000 MT Desktop |
| Network Attachment | Internal Network |
| Internal Network Name | `IT-LAB` |
| IPv4 Address | `192.168.50.20/24` |

### Domain Configuration

The Windows 11 client is joined to the Active Directory domain:

- Domain: `ad.lab.test`
- DNS Server: `192.168.50.10`

## Virtual Network Configuration

Both virtual machines use the following VirtualBox network configuration:

| Parameter | Configuration |
|---|---|
| Network Type | Internal Network |
| Network Name | `IT-LAB` |
| Adapter Model | Intel PRO/1000 MT Desktop |
| Promiscuous Mode | Deny |
| Cable Connected | Yes |
| Network Subnet | `192.168.50.0/24` |

The internal network provides connectivity between the virtual machines without directly connecting this network adapter to the physical network.

## Resource Summary

| Resource | WS2022-LAB | LAB-CLIENT01 |
|---|---|---|
| RAM | 4 GB | 4 GB |
| Virtual CPUs | 2 | 2 |
| Firmware | UEFI | UEFI |
| Secure Boot | Disabled | Enabled |
| TPM | Not configured | TPM 2.0 |
| Chipset | PIIX3 | PIIX3 |

## Current Scope

The documentation describes the current VirtualBox configuration of both lab machines.

The environment consists of one Windows Server 2022 virtual machine and one Windows 11 Pro virtual machine.

Additional virtual machines may be introduced as the lab develops.
