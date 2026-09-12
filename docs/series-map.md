# Series map

Every topology = three episodes: **A budget**, **B harden**, **C weather + IR**.
Videos ≤ 8 minutes (4 + 4). Extra plate is this repo.

**Close the loop:** do not film the next fabric until the current C episode has a filled ticket, detections page, and AAR.

Phones before money. 04 owns the air (Spitz) and the herd (MDM). 05 is the till. Those names belong *after* the desk exists on camera.

## Status

| Topology | Plain name | Status |
| --- | --- | --- |
| 01 | Desk | Open |
| 02 | House | Locked until 01 AAR |
| 03 | Door | Locked |
| 04 | Air + phones | Locked |
| 05 | Till | Locked |

## Topology 01 — desk

Folder: [topologies/01-ros](topologies/01-ros/)

Carrier box + TL-SG108E + ThinkPad + AX17 (Parrot + Wazuh). One visibility point.

| Ep | Job | Repo close |
| --- | --- | --- |
| 1A | Budget the desk. Packet Tracer in `assets/`. | BOM + do-not-buy list |
| 1B | Harden. Quiet Wazuh. | Healthy screenshot in assets |
| 1C | Willy. IR close. | ticket.md + detections.md + aar.md |

## Topology 02 — house

Folder: [topologies/02-slate-nat](topologies/02-slate-nat/)

Slate AX as NAT #2 *for now*. G11 NAS. Office SSID on the Slate. Carrier still the radio. Do not jump the SIM here.

| Ep | Job |
| --- | --- |
| 2A | Budget Slate + G11. |
| 2B | Double NAT named. Share opens. |
| 2C | Weather. Brick is still the landlord. |

## Topology 03 — door

Folder: [topologies/03-two-sensors](topologies/03-two-sensors/)

Path mini PC: blast bridge, Wazuh, inspect. Pi = chair. AX17 freed for 04.

| Ep | Job |
| --- | --- |
| 3A | Budget the path PC. Dual RJ45. |
| 3B | Bridge. Move Wazuh. Pi on VLAN 40. |
| 3C | Leroy vs path + chair. |

## Topology 04 — own the air + own the phones

Folder: [topologies/04-mdm](topologies/04-mdm/)

**GL-X3000 Spitz AX** takes the T-Mobile SIM. Carrier gateway shelves. Slate demoted to **dirty AP** (VLAN 20: IoT, guests, printers). MDM on AX17. Prepaid herd on VLAN 50.

| Ep | Job |
| --- | --- |
| 4A | Budget Spitz. Brick dies. Slate demoted, not dumped. MDM named. |
| 4B | SIM in Spitz. Office SSID on Spitz. Slate on 20. Enroll phones. |
| 4C | Weather on *our* radio. IR close. |

## Topology 05 — till

Folder: [topologies/05-till](topologies/05-till/)

Mac mini on VLAN 60. After 5C: SIEM + MDM + files + till. Yellowjackets may knock.

| Ep | Job |
| --- | --- |
| 5A | Budget the money box. |
| 5B | VLAN 60 deny list. |
| 5C | Office exists. |
