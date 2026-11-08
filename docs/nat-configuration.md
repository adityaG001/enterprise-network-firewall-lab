# NAT Configuration Notes

**Status:** Planned.

## Outbound NAT
Begin with the platform's automatic outbound NAT mode for this isolated lab. Inspect the generated mappings and document the source network, translated address and egress interface.

## Port forwarding
If a port-forward exercise is required, forward a high test port on the isolated lab WAN to the DMZ test server. Do not expose Juice Shop, DVWA or other vulnerable applications to the public Internet or a real home network.

Document:
- Ingress interface
- Protocol and destination port
- Redirect target IP and port
- Associated filter rule
- Test source and observed result

## Concepts to explain
- SNAT: translates source addresses, commonly for outbound connectivity.
- DNAT: translates destination addresses, commonly for port forwarding.
- NAT is not a substitute for firewall policy; validate the associated filtering behavior.
