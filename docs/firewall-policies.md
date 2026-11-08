# Firewall Policy Matrix

**Status:** Proposed baseline. Record the final interface, rule order, counters and test result after implementation.

| Ingress zone | Source | Destination | Service | Intended action | Rationale |
|---|---|---|---|---|---|
| LAN | LAN net | DMZ web host | TCP 80/443 | Allow | Application access |
| LAN | LAN net | DMZ net | Any other | Block | Least privilege |
| DMZ | DMZ net | LAN net | Any | Block | Prevent DMZ-to-LAN lateral movement |
| DMZ | DMZ host | Approved update/DNS destinations | Required ports | Allow narrowly | Controlled egress |
| WAN | Any | LAN/DMZ | Any unsolicited | Block | Default-deny inbound |

## Implementation checklist
- [ ] Confirm interface assignments and interface names.
- [ ] Configure LAN and DMZ interface addresses.
- [ ] Add narrowly scoped allow rules.
- [ ] Confirm default-deny behavior.
- [ ] Verify rule ordering and state table behavior.
- [ ] Test both allowed and denied flows.
- [ ] Capture screenshots with secrets and public IPs redacted.

## Results
Do not mark a policy as validated until the matching test has been executed. Add date, source, destination, protocol, expected result, actual result and evidence filename.
