# Architecture and Lab Design

**Status:** Design draft; validate interface names and addressing during installation.

## VirtualBox networks
| Adapter | OPNsense attachment | Purpose |
|---|---|---|
| 1 | NAT | WAN connectivity for updates |
| 2 | Internal Network `LAB-LAN` | Trusted test client network |
| 3 | Internal Network `LAB-DMZ` | Isolated server network |

Attach Kali to `LAB-LAN` and Ubuntu Server to `LAB-DMZ`. Do not bridge the vulnerable lab networks to a physical LAN.

## Addressing plan
| Segment | Gateway | Example host |
|---|---|---|
| LAN `192.168.10.0/24` | `192.168.10.1` | Kali `192.168.10.10` |
| DMZ `192.168.20.0/24` | `192.168.20.1` | Ubuntu `192.168.20.10` |
| WAN | DHCP | VirtualBox NAT |

These are proposed lab addresses, not evidence of a completed deployment.

## Traffic-flow goals
- LAN to DMZ: allow only explicitly required application ports.
- DMZ to LAN: deny by default.
- DMZ to WAN: allow only required outbound services.
- WAN to internal zones: deny unsolicited inbound traffic.
- Firewall administration: allow only from the designated management client.

## Design considerations
- OPNsense rules are stateful and evaluated on the interface where traffic enters.
- Rule order and automatically generated anti-lockout rules must be reviewed.
- Add DNS, NTP and update access deliberately; avoid broad `any/any` rules.
- Keep a backup of the configuration before major changes.
