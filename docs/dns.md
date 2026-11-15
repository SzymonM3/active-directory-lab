# DNS Configuration

## Overview

The lab uses the DNS Server role hosted on the domain controller `LAB-DC01`.

DNS provides name resolution for the Active Directory domain `ad.lab.test` and supports domain-related services.

| Parameter | Value |
|---|---|
| DNS Server | LAB-DC01 |
| DNS Server IPv4 Address | 192.168.50.10 |
| Client DNS Server | 192.168.50.10 |
| Domain DNS Name | ad.lab.test |

## DNS Zones

The DNS server hosts the following zones:

| Zone Name | Zone Type | Active Directory Integration | Replication Scope |
|---|---|---|---|
| `ad.lab.test` | Primary | Yes | Domain |
| `_msdcs.ad.lab.test` | Primary | Yes | Forest |
| `TrustAnchors` | Primary | Yes | Forest |
| `0.in-addr.arpa` | Primary | No | Not applicable |
| `127.in-addr.arpa` | Primary | No | Not applicable |
| `255.in-addr.arpa` | Primary | No | Not applicable |

The `ad.lab.test` and `_msdcs.ad.lab.test` zones are Active Directory-integrated.

## DNS Client Configuration

The domain controller uses loopback addresses for its DNS configuration:

- IPv4: `127.0.0.1`
- IPv6: `::1`

The Windows 11 client uses `192.168.50.10` as its DNS server.

## DNS Forwarding

No manually configured DNS forwarder addresses are present.

The DNS server uses Root Hints:

| Parameter | Value |
|---|---|
| Use Root Hints | Enabled |
| Timeout | 3 seconds |
| Enable Reordering | Enabled |
| Manual Forwarder Addresses | None |

## Network Considerations

- The DNS server is hosted on the domain controller.
- The Windows client uses the domain controller for DNS resolution.
- The lab network is an isolated VirtualBox Internal Network.
- No default gateway is configured on either virtual machine.

## Current Scope

The current DNS configuration includes the domain-related zones and default DNS zones listed above.

No reverse lookup zone for `192.168.50.0/24` is currently configured.

Further DNS configuration and troubleshooting scenarios may be documented as the lab develops.
