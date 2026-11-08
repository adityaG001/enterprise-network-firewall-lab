# Suricata IDS/IPS Plan

**Status:** Planned.

## Rollout
1. Install the OPNsense intrusion-detection plugin if available for the selected release.
2. Select the appropriate monitored interface(s).
3. Enable a maintained ruleset whose terms permit your use.
4. Start in IDS/alert-only mode.
5. Generate controlled traffic within the isolated lab.
6. Review signature, classification, source/destination, timestamp and action.
7. Investigate false positives before considering IPS mode.
8. Enable blocking only after verifying interface support and expected traffic behavior.

## Evidence to collect
- Plugin and engine version
- Interface and mode
- Ruleset name and update date
- Alert signature and SID
- Source/destination and protocol
- Why the alert occurred
- Whether it was a true positive or false positive
- Retest result after any tuning

Do not claim an alert was blocked unless the logs and packet/connection test confirm blocking.
