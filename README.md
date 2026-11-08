# Enterprise Network Firewall & IDS/IPS Lab

**Owner:** [adityaG001](https://github.com/adityaG001)  
**Status:** `Planned` — implementation and test evidence will be added as the lab is completed.

A hands-on network security lab for designing segmented networks, administering firewall policies, configuring NAT, and monitoring traffic with Suricata.

## Objectives
- Build WAN, LAN, and DMZ zones using OPNsense.
- Apply least-privilege, stateful firewall policies.
- Configure outbound NAT and controlled port forwarding.
- Deploy Suricata in alert-only mode first, then validate IPS blocking.
- Record test results, alerts, and policy changes.

## Lab topology

```text
             Internet (VirtualBox NAT)
                       |
                    [ WAN ]
                  OPNsense
              [ LAN ]   [ DMZ ]
                 |         |
               Kali     Ubuntu Server
          192.168.10.10 192.168.20.10
```

## Planned components
| Component | Role |
|---|---|
| OPNsense | Stateful firewall, routing, NAT, policy enforcement |
| Kali Linux | Authorized test client and traffic generation |
| Ubuntu Server | DMZ host / test web server |
| Suricata | Network IDS/IPS |
| Wireshark | Packet inspection and troubleshooting |

## Repository layout
- `docs/` — architecture, addressing, policies, NAT and IDS/IPS notes
- `configs/` — sanitized configuration examples (never upload secrets)
- `testing/` — reproducible validation procedures and result templates
- `diagrams/` — network diagrams
- `screenshots/` — redacted evidence captured during implementation
- `reports/` — final findings and lessons learned

## Getting started
1. Read [`docs/architecture.md`](docs/architecture.md).
2. Build the isolated VirtualBox networks described there.
3. Install OPNsense and assign WAN/LAN/DMZ interfaces.
4. Implement the policy matrix in [`docs/firewall-policies.md`](docs/firewall-policies.md).
5. Complete the test cases in `testing/` and record actual outcomes.

## Safety and scope
This lab is for systems you own or are explicitly authorized to test. Keep vulnerable services and test networks isolated from your home/work networks and the public Internet. Do not expose the management interface or vulnerable targets publicly.

## Evidence policy
Screenshots, logs and results will be added only after the corresponding tests have actually been run. No simulated results are presented as completed work.

## References
- [OPNsense documentation](https://docs.opnsense.org/)
- [OPNsense firewall rules](https://docs.opnsense.org/manual/firewall.html)
- [Suricata documentation](https://docs.suricata.io/)
