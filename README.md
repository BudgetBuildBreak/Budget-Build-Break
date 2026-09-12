# Budget. Build. Break.

**Budget the build. Secure the network. Then we break it.**

YouTube: [Budget. Build. Break.](https://www.youtube.com/@BudgetBuildBreak)

This repo is the packet. YouTube is the trailer.

Small-office and home-network lab notes: budget bills of materials, VLAN segmentation, Wazuh visibility, later MDM. Each fabric is a network you can copy. We break *this* topology and write what the logs showed.

Beginners searching **home lab**, **SoHo firewall**, **cheap managed switch**, **Wazuh home network**, **guest Wi-Fi isolation** — start at Topology 01. Codenames (Desk, House, Till) are for memory. The plain names in the table are for search.

## Start here (do this first)

Build **Topology 01 — Desk** (home-lab desk: ISP gateway + managed switch + two PCs + Wazuh). Topology 02 stays locked until the 01 AAR is *filled*, not just created.

| Question | Answer for 01 |
| --- | --- |
| What office is this? | One desk. Carrier home gateway, a $28 managed switch, a user laptop, a used box running Wazuh. |
| What did it cost? | See [docs/topologies/01-ros/bom.md](docs/topologies/01-ros/bom.md). Prices rot. The job of each SKU does not. |
| What do we attack? | Named in the 1C ticket after it is written. Not before. |
| What should we see? | A host or identity IoC **and** a network IoC. Packet-only is a miss. |
| Is the AAR done? | **No.** [aar.md](docs/topologies/01-ros/aar.md) is a template. Status line at the top of that file is the source of truth. |

Case file: [`docs/topologies/01-ros/`](docs/topologies/01-ros/)

## Fabrics

Codename after the facts. Search terms sit next to the codename on purpose.

| # | Codename | Search / plain name | Status | Folder | One sentence |
| --- | --- | --- | --- | --- | --- |
| 01 | Desk | Home lab desk, ISP gateway, cheap managed switch, Wazuh all-in-one | **Scaffolding.** AAR template exists. Not shipped. 02 locked until 1C AAR has facts. | [01-ros](docs/topologies/01-ros/) | See a port. One visibility point. |
| 02 | House | Double NAT, travel router, home NAS, office SSID | Locked until 01 AAR is filled | [02-slate-nat](docs/topologies/02-slate-nat/) | Second NAT + NAS. Carrier still WAN. |
| 03 | Door | Network bridge, SIEM on the path, honeypot Pi | Locked | [03-two-sensors](docs/topologies/03-two-sensors/) | Bridge + Wazuh on a path box. Pi is a chair. |
| 04 | Air + phones | 5G / T-Mobile SIM router, guest Wi-Fi AP, MDM, Android fleet | Locked | [04-mdm](docs/topologies/04-mdm/) | Own the SIM and the herd. Dirty AP is demoted, not dumped. |
| 05 | Till | Isolated money PC, payment VLAN, small-office segmentation | Locked | [05-till](docs/topologies/05-till/) | Money box. Yellowjackets only after PII and cash move. |

Rule: next topology is the mitigation of the last C episode.

Map: [`docs/series-map.md`](docs/series-map.md) · VLANs: [`docs/vlan-plan.md`](docs/vlan-plan.md) · Ground rules: [`docs/lab-ground-rules.md`](docs/lab-ground-rules.md)

## Episode contract

Runtime ≤ 8 minutes on camera. Extra plate lives here.

| Beat | Job |
| --- | --- |
| A Budget | SKU, cap, what got cut, what visibility you lost. |
| B Harden | From zero. Healthy screenshot. |
| C Weather + IR | Named attack on *this* path. Ticket + detections + **filled** AAR. |

Templates: [`templates/ticket.md`](templates/ticket.md) · [`templates/detections.md`](templates/detections.md) · [`templates/threat-model.md`](templates/threat-model.md)

Every C episode must produce **one host or identity IoC**, not only a firewall drop.

## Clone

```bash
git clone https://github.com/BudgetBuildBreak/Budget-Build-Break.git
cd Budget-Build-Break
```

[CC BY 4.0](LICENSE). Credit the channel. Remix the notes. Do not pretend the prices are still current.

Hiring / reproduce-in-a-weekend notes: [`docs/candidate.md`](docs/candidate.md)
