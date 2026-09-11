# BOM — Topology 01

Date priced: 2026-09-11
Currency: USD

Starter house: carrier box, cheap smart switch, ThinkPad as the user, AX17 Pro as Wazuh looking at a mirror port. AX17 has no RJ45 — one cheap USB3 gigabit dongle.

Not textbook RoS. The SG108E is the stick and the span.

## Cash this week vs replacement

| Line | Cash this week | Replacement street |
| --- | --- | --- |
| New silicon | **$37.98** (switch + USB NIC) | ~$920–1,000 |
| Recurring WAN | carrier plan | below |

## Hardware

| Qty | Item | Role | Street (this date) | Cash | Notes |
| --- | --- | --- | --- | --- | --- |
| 1 | ATT / T-Mobile / Verizon home internet gateway | WAN + default LAN | $0 with plan | $0 | No 802.1Q trunk. CGNAT likely. |
| 1 | TP-Link TL-SG108E | VLANs + port mirror | $27.99 cart / $29.99 list | $27.99 | Easy Smart. Mirror is built in. [Amazon](https://www.amazon.com/TP-LINK-TL-SG108E-8-Port-Gigabit-Tag-Based/dp/B00K4DS5KU/) |
| 1 | Lenovo ThinkPad Ryzen 5 7535U, 16 GB | Host user, VLAN 10 | owned — used replace ~$575 | $0 | Has NIC. This is the person. |
| 1 | AX17 Pro R3-4300U, 16 GB / 512 GB | Wazuh box | owned — replace ~$309 | $0 | No RJ45. Lives on the span, not as the guest victim. |
| 1 | USB 3.0 to Gigabit Ethernet | Span NIC for AX17 | **~$9.99** | $9.99 | USB-A or USB-C to RJ45, 1000 Mbps. Amazon Basics / BENFEI / generic in the $8–13 bin. Do not buy a $40 hub. |

**Cash this week:** $37.98 + tax  
**Replace-all silicon (gateway bundled):** ~$922

## Recurring

| Item | Typical |
| --- | --- |
| Home internet plan | ~$50–70 / mo |

Wazuh itself is free software. Price the compute you already own, not a license.

## Port map (TL-SG108E)

| Port | Job | Plugs in |
| --- | --- | --- |
| 1 | Uplink | ISP gateway LAN |
| 2 | VLAN 10 access | ThinkPad (user) |
| 3 | Mirror *destination* | AX17 USB NIC (Wazuh sees copies) |
| 4–8 | Dark | Future guest / AP / camera |

Mirror source: port 2 (and port 1 later if we want WAN-side noise). SG108E can span across VLANs. Older firmware is picky about how many sources — start with one source, one dest.

AX17 management path: Wi-Fi to the carrier LAN so the USB NIC can stay promiscuous on the span and not need a second dongle. If Wi-Fi is too dirty for the story, buy a *second* $10 NIC later and put it on an access port. Not today.

## What this fabric can do

- User on 10, sensor watching 10.
- First Wazuh dashboard on hardware that cost three figures used.
- “Healthy” screenshot before any wasp weather.

## What this fabric cannot do yet

- Guest victim laptop (AX17 is the camera now, not the wasp).
- Classic RoS on the carrier brick.
- Full packet capture appliance.

## Substitutions

- Any USB3 **gigabit** dongle ~$10. Skip 10/100-only.
- Same switch family: SG105E / SG108E / SG116E.

## What we refused to buy

- USB-C dock.
- Dedicated sensor appliance.
- Second laptop just for mgmt.
