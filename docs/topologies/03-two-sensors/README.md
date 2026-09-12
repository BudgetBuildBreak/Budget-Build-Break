# Topology 03 — blast bridge + chair

Mitigation of 02C. Dual-NIC mini PC **behind the Slate, in front of the switch**. No NAT #3.

Wazuh + packet inspection live here. Slate syslog points here. AX17 is freed for topology 04 MDM. **Pi** is the honeynet (empty chair, VLAN 40). Not a PII honey. Yellowjackets wait for 05.

## Roles

| Box | Job |
| --- | --- |
| ISP gateway | NAT #1 untrusted |
| Slate AX | NAT #2, office SSID, logs → path PC |
| Path mini PC | Blast bridge, Wazuh, inspect |
| SG108E | Trunk from bridge, access to hosts |
| ThinkPad | User VLAN 10 |
| G11 | NAS VLAN 30. NIC2 optional spare span |
| Pi | Chair VLAN 40 |
| AX17 | Idle this fabric / prepped for MDM |

## Diagram

```
ISP → Slate → [path PC bridge + Wazuh] → SG108E
                                    → ThinkPad
                                    → G11
                                    → Pi chair
```

## Trilogy

3A budget the path PC (two real RJ45s).
3B bridge, move Wazuh, inspect into one console, Pi on 40.
3C Leroy vs path + chair. IR close.
