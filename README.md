# Active Directory Helpdesk Lab

## Project Overview

This repository documents a virtual IT infrastructure lab built with Oracle VirtualBox.

The environment consists of two virtual machines running Windows Server 2022 and Windows 11 Pro. They are connected through an isolated VirtualBox Internal Network and configured as a domain-based environment.

The lab is used to explore and document:

- Windows Server administration
- Active Directory Domain Services (AD DS)
- DNS configuration and name resolution
- Domain users and security groups
- SMB file sharing
- NTFS and share permissions
- Windows client administration
- Helpdesk troubleshooting scenarios

The repository is gradually extended with infrastructure documentation and practical administration scenarios.

## Infrastructure Overview

| Component | Configuration |
|---|---|
| Virtualization Platform | Oracle VirtualBox |
| Domain | `ad.lab.test` |
| Domain Controller | `LAB-DC01` |
| Domain Client | `LAB-CLIENT01` |
| Network | `IT-LAB` |
| Network Subnet | `192.168.50.0/24` |

The environment consists of:

- **LAB-DC01** — Windows Server 2022, providing AD DS, DNS and File Server services.
- **LAB-CLIENT01** — Windows 11 Pro, joined to the Active Directory domain.

## Infrastructure Diagram

The diagram below presents the current lab topology.

See [Infrastructure Diagram](diagrams/infrastructure.md).

## Documentation

Detailed configuration and architecture documentation is available below.

| Document | Description |
|---|---|
| [Lab Architecture](docs/architecture.md) | Infrastructure topology, network and domain overview |
| [Active Directory Configuration](docs/active-directory.md) | Domain structure, users, security groups and FSMO roles |
| [DNS Configuration](docs/dns.md) | DNS zones, integration and forwarding configuration |
| [File Server Configuration](docs/file-server.md) | SMB share and NTFS permissions |
| [Virtual Machine Configuration](docs/virtual-machines.md) | VirtualBox settings and VM resources |

## Repository Structure

```text
active-directory-lab/
├── README.md
├── docs/
│   ├── architecture.md
│   ├── active-directory.md
│   ├── dns.md
│   ├── file-server.md
│   └── virtual-machines.md
├── diagrams/
│   └── infrastructure.md
├── screenshots/
│   ├── virtualbox/
│   ├── server/
│   └── client/
└── incidents/
```

## Helpdesk Incidents

The `incidents/` directory is reserved for practical helpdesk incidents and troubleshooting scenarios.

Each incident will be documented separately, including the observed problem, investigation, troubleshooting steps and resolution where applicable.

Additional scenarios will be added as the lab develops.

## Project Status

**Status: In Progress**

The basic domain environment has been configured and documented.

Current work focuses on expanding the infrastructure documentation and gradually adding practical Windows administration and helpdesk scenarios.

