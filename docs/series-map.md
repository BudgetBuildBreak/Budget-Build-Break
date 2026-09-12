# Series map

Every topology = three episodes. A budget. A harden. A wasp + IR. The next topology is the mitigation.

## Topology 01 — carrier box, SG108E, two laptops

Folder: [topologies/01-ros](topologies/01-ros/)

| Ep | Status | Title | Job |
| --- | --- | --- | --- |
| 1A | planned | Budget the desk | Laptops we own. Why the TL-SG108E. Carrier is a start, not a home. Packet Tracer recipe in the repo. |
| 1B | planned | Harden from zero | ThinkPad firewall. Parrot + Wazuh on AX17. Switch + span. Quiet dashboard. |
| 1C | planned | Willy walks in | First wasp. Thin security on this desk. IR close. |

Visibility this fabric: **one point** — Wazuh on the AX.

## Topology 02 — Slate AX + G11 NAS

Folder: [topologies/02-slate-nat](topologies/02-slate-nat/)

Mitigation of 01C. Brain + disk + office SSID. **No packet IDS yet.** Second NIC on the G11 is bought and left dark on purpose.

| Ep | Status | Title | Job |
| --- | --- | --- | --- |
| 2A | planned | Budget the house | Slate AX $119. G11 $309.99. Dual NIC is future tap, not this trilogy. |
| 2B | planned | Harden the Slate | NAT #2. Office SSID. G11 share. Wazuh still one console. |
| 2C | planned | Weather on the new house | Wasp vs mitigated fabric. Lessons that justify a second sensor. |

Visibility this fabric: still **one point** — Wazuh. That is how we learn what a single dashboard misses.

## Topology 03 — second visibility point

Folder: [topologies/03-two-sensors](topologies/03-two-sensors/)

Mitigation of 02C. Packet IDS VM on G11 NIC2. Alerts into Wazuh. Two points so toy-class weather (Leroy) that slips an untuned dashboard still has to clear a tap.

| Ep | Status | Title | Job |
| --- | --- | --- | --- |
| 3A | planned | Budget the tap | VM on hardware we already own. No new silicon unless 02C demanded it. |
| 3B | planned | Harden two feeds | Span to G11 NIC2. IDS VM. Decoders in Wazuh. Tune until both disagree less. |
| 3C | planned | Leroy vs two points | Toy-class weather. Show a miss on one feed and a hit on the other. IR close. |

## Later

Do not schedule 04 until 03C has three bullets in lessons.md.
