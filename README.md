# Budget. Build. Break.

**Budget the build. Secure the network. Then we break it.**

YouTube: [Budget. Build. Break.](https://www.youtube.com/@BudgetBuildBreak)

This repo is the packet. YouTube is the trailer.

Each fabric is a small-office / home-office network you can copy: cheapest box that still has a job, then we attack *this* topology and write what the logs actually showed.

## Start here (do this first)

Close **Topology 01 — Desk** before you build 02.

| Question | Answer for 01 |
| --- | --- |
| What office is this? | One desk. Carrier home gateway, a $28 managed switch, a user laptop, a used box running Wazuh. |
| What did it cost? | See [docs/topologies/01-ros/bom.md](docs/topologies/01-ros/bom.md). Prices rot. The job of each SKU does not. |
| What do we attack? | A walk-on on *this* trunk / guest / mgmt split. Named in the 1C ticket. |
| What should we see? | A host or identity IoC **and** a network IoC. Packet-only is a miss. |

Case file: [`docs/topologies/01-ros/`](docs/topologies/01-ros/)

## Fabrics

Codename after the facts.

| # | Plain name | Status | Folder | One sentence |
| --- | --- | --- | --- | --- |
| 01 | Desk | **Open — ship the AAR before 02** | [01-ros](docs/topologies/01-ros/) | See a port. One visibility point. |
| 02 | House | Locked until 01 AAR | [02-slate-nat](docs/topologies/02-slate-nat/) | Second NAT + NAS. Carrier still WAN. |
| 03 | Door | Locked | [03-two-sensors](docs/topologies/03-two-sensors/) | Bridge + Wazuh on a path box. Pi is a chair. |
| 04 | Air + phones | Locked | [04-mdm](docs/topologies/04-mdm/) | Own the SIM and the herd. Dirty AP is demoted, not dumped. |
| 05 | Till | Locked | [05-till](docs/topologies/05-till/) | Money box. Yellowjackets only after PII and cash move. |

Rule: next topology is the mitigation of the last C episode. Do not outline season five while episode 1C has an empty ticket.

Map: [`docs/series-map.md`](docs/series-map.md) · VLANs: [`docs/vlan-plan.md`](docs/vlan-plan.md) · Ground rules: [`docs/lab-ground-rules.md`](docs/lab-ground-rules.md)

## Episode contract

Runtime ≤ 8 minutes on camera. Extra plate lives here.

| Beat | Job |
| --- | --- |
| A Budget | SKU, cap, what got cut, what visibility you lost. |
| B Harden | From zero. Healthy screenshot. |
| C Weather + IR | Named attack on *this* path. Ticket + detections + AAR. |

Templates: [`templates/ticket.md`](templates/ticket.md) · [`templates/detections.md`](templates/detections.md) · [`templates/threat-model.md`](templates/threat-model.md)

Every C episode must produce **one host or identity IoC**, not only a firewall drop.

## Clone

```bash
git clone https://github.com/BudgetBuildBreak/Budget-Build-Break.git
cd Budget-Build-Break
```

[CC BY 4.0](LICENSE). Credit the channel. Remix the notes. Do not pretend the prices are still current.

Hiring / reproduce-in-a-weekend notes: [`docs/candidate.md`](docs/candidate.md)
