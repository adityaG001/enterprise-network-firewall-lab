# Nmap Validation

Run scans only against your own lab hosts.

Example service discovery against the DMZ host:

```bash
nmap -sV -Pn 192.168.20.10
```

For each run, record:
- Nmap version and exact command
- Scan source and target
- Ports observed
- Firewall rule expected to govern the traffic
- Whether the observed result matched the policy

Do not interpret a filtered port as proof of a specific firewall rule without checking firewall logs and packet captures.
