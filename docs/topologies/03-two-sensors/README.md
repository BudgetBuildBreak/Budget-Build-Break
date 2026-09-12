# Topology 03 — blast bridge + honeynet

Mitigation of 02C. New mini PC sits **behind the Slate and in front of the switch**. No NAT #3. AX17 leaves the Wazuh job and becomes a decoy on the switch.

This honeynet is an **empty chair for wasps**, not a Yellowjacket season. No customer records. No money. If 03C needs PII honey, that is a later topology and a different gate.

## Roles

| Box | Job |
| --- | --- |
| ISP gateway | Untrusted radio. NAT #1. |
| Slate AX | NAT #2. Office SSID. Too small to be the SIEM. |
| **New mini PC** | Blast bridge. Wazuh. Packet inspection. Dual NIC. |
| TL-SG108E | Inside switch |
| ThinkPad | Host user |
| G11 | NAS. NIC2 optional span if the bridge is not the only tap. |
| **AX17** | Honeynet / decoy on the switch. Parrot or whatever 3B images. Not the dashboard. |

## Why the path box gets Wazuh

Everything into the house walks through it. Logs and packets can meet on one machine without a $10 NIC and a prayer. The AX 4300U was a starter sensor. 03 is where the evidence plane grows up.

Packet inspection on that same box: IDS/metadata engine **feeding Wazuh**, not a second console. Bridge first. Detect second. Do not inline-break the NAS; the NAS stays on the switch, south of the bridge.

## Diagram

```
[ ISP box ]                    NAT #1
    |
[ Slate AX ]                   NAT #2  office SSID
    |
    | Slate LAN
    v
[ Mini PC NIC A ]
[ Blast bridge + Wazuh + inspect ]     no extra NAT
[ Mini PC NIC B ]
    |
[ TL-SG108E ]
    |          |           |
 ThinkPad     G11 NAS     AX17 honeynet
 user                     empty chair
```

## Trilogy

**3A Budget.** Second mini PC, dual NIC, same Amazon lottery. Say out loud: AX17 is no longer the SIEM.

**3B Harden.** Bridge up. Wazuh moved. Inspection feeding the dashboard. AX17 rebuilt as decoy. ThinkPad still opens the G11 share.

**3C Weather + IR.** Leroy / household. One feed on the path, decoy on the switch. IR close.

## Two points (updated)

| Point | Where |
| --- | --- |
| 1 | Wazuh + inspection on the blast bridge |
| 2 | AX17 honeynet (what landed) and/or G11 NIC2 span if 3B still wants a copy off-path |

Do not stand up three packet engines in 3B. Path inspect + decoy is enough. Span on G11 is spare.

## Cookbook

- [BOM](bom.md)
- [lessons.md](lessons.md)
