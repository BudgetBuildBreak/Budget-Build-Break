# Series map

Every topology = three episodes: **A budget**, **B harden**, **C weather + IR**.
Videos ≤ 8 minutes (4 + 4). Extra plate is this repo.

Phones before money. MDM is 04. Till is 05.

## Topology 01 — desk

Folder: [topologies/01-ros](topologies/01-ros/)

Carrier box + TL-SG108E + ThinkPad (user) + AX17 (Parrot + Wazuh on the span). One visibility point.

| Ep | Job |
| --- | --- |
| 1A | Budget the desk. Switch why. Carrier is a start. Packet Tracer recipe in `assets/`. |
| 1B | Harden. Firewalls. Parrot + Wazuh. Packets on the span. Quiet dashboard. |
| 1C | Willy. Thin security on this desk. IR close. |

## Topology 02 — house

Folder: [topologies/02-slate-nat](topologies/02-slate-nat/)

Slate AX ($119) NAT #2. G11 NAS ($309.99). Office SSID. G11 NIC2 stays dark. AX still Wazuh.

| Ep | Job |
| --- | --- |
| 2A | Budget Slate + G11. Amazon lottery. Dual NIC is a promise for later. |
| 2B | Harden. Double NAT named. Share opens. Carrier SSID parked. |
| 2C | Weather. One dashboard is not enough. |

## Topology 03 — door

Folder: [topologies/03-two-sensors](topologies/03-two-sensors/)

New dual-NIC mini PC: blast bridge, **no NAT #3**. Wazuh + inspection move here. Slate syslog → this box. Pi = honeynet (empty chair). AX17 freed for 04.

| Ep | Job |
| --- | --- |
| 3A | Budget the path PC. Dual real RJ45. |
| 3B | Bridge. Move Wazuh. Inspect feeds Wazuh. Pi on the chair VLAN. |
| 3C | Leroy vs path inspect + chair. IR close. |

## Topology 04 — phones

Folder: [topologies/04-mdm](topologies/04-mdm/)

MDM on the AX17 (stays on the LAN). Prepaid Androids on Slate Wi-Fi, VLAN 50. Headwind and/or Fleet — pick in 4A by pocket mix.

| Ep | Job |
| --- | --- |
| 4A | Budget MDM (time + phones you already burn). |
| 4B | Enroll the herd. SSID + VLAN 50. |
| 4C | Weather on the radio. IR close. |

## Topology 05 — till

Folder: [topologies/05-till](topologies/05-till/)

Mac mini (or locked SKU) on VLAN 60. No lab share. No chair. No guest. Isolation is the control, not the logo.

| Ep | Job |
| --- | --- |
| 5A | Budget the money box. |
| 5B | Harden VLAN 60. Pinholes only. |
| 5C | Office exists: SIEM + MDM + files + till. Yellowjackets may now have a door. |

## Optional stitch

One interstitial harden video *after a C* if devices are sloppy and the next A is not ready. Same 4+4. Cookbook takes the rest.

Do not schedule 06 until 05C has three bullets in lessons.md.
