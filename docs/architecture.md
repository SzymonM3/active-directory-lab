# Lab Architecture

## Overview

The lab environment consists of two virtual machines running in Oracle VirtualBox.

Both machines are connected to an isolated VirtualBox Internal Network named `IT-LAB`. The network allows communication between the domain controller and the Windows client without requiring an external network connection.

## Infrastructure Topology

| Component | Hostname | IP Address | Function |
|---|---|---|---|
| Windows Server 2022 | LAB-DC01 | 192.168.50.10 | Domain Controller, DNS Server, File Server |
| Windows 11 Pro | LAB-CLIENT01 | 192.168.50.20 | Domain-joined client |

## Network Topology

- Network type: VirtualBox Internal Network
- Network name: `IT-LAB`
- Network address: `192.168.50.0/24`
- Default gateway: Not configured
- Domain DNS server: `192.168.50.10`

Both virtual machines use the same network segment.

## Domain Infrastructure

The Windows Server machine (`LAB-DC01`) hosts the Active Directory domain:

- Domain: `ad.lab.test`
- NetBIOS name: `AD`
- Domain Controller: `LAB-DC01.ad.lab.test`

The Windows 11 client (`LAB-CLIENT01`) is joined to this domain and uses the domain controller as its DNS server.

## Infrastructure Roles

### LAB-DC01

The server provides the following services:

- Active Directory Domain Services (AD DS)
- DNS Server
- File Server

### LAB-CLIENT01

The client machine is used to test domain-related functionality, including:

- Domain membership
- Domain user authentication
- Access to network resources
- File share permissions

## Design Considerations

- The lab is isolated using a VirtualBox Internal Network.
- Both machines operate within the same IPv4 subnet.
- The domain controller provides DNS resolution for the domain environment.
- The Windows client uses the domain controller for DNS.
- No default gateway is configured on either machine.

## Future Extensions

The environment can be extended with additional virtual machines, infrastructure services and documented helpdesk scenarios.
