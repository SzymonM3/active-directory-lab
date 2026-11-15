
# Infrastructure Diagram

The diagram presents the current virtual lab topology.

```mermaid
flowchart TB
    subgraph VBOX["Oracle VirtualBox"]
        subgraph NET["Internal Network: IT-LAB | 192.168.50.0/24"]
            DC["LAB-DC01<br/>Windows Server 2022<br/>192.168.50.10"]

            CLIENT["LAB-CLIENT01<br/>Windows 11 Pro<br/>192.168.50.20"]

            DC -->|"DNS: ad.lab.test"| CLIENT
            CLIENT -->|"Domain authentication<br/>and network resource access"| DC
        end
    end

    subgraph SERVICES["Services hosted on LAB-DC01"]
        AD["Active Directory Domain Services<br/>Domain: ad.lab.test"]
        DNS["DNS Server"]
        FS["File Server<br/>SMB: LabShare"]
    end

    DC --- AD
    DC --- DNS
    DC --- FS
```

## Network Details

| Component | Configuration |
|---|---|
| Virtualization Platform | Oracle VirtualBox |
| Network Type | Internal Network |
| Network Name | `IT-LAB` |
| Network Subnet | `192.168.50.0/24` |
| Domain | `ad.lab.test` |
| Domain Controller | `LAB-DC01` |
| Domain Client | `LAB-CLIENT01` |

## Diagram Scope

The diagram represents the current two-machine lab environment.

Both virtual machines are connected to the same isolated VirtualBox Internal Network. The domain controller provides Active Directory, DNS and SMB file sharing services.

No Internet connection, router, DHCP server or additional domain controller is represented.

