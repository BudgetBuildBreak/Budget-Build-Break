# BOM — Topology 01

Date priced: 2026-09-11
Currency: USD

This is the simple house: carrier home-internet box, one cheap smart switch, two budget laptops. It is **not** a textbook router-on-a-stick (no subinterfaces on the ISP gateway). The stick lesson still holds: one uplink, VLANs on the TL-SG108E, two rooms that should not share a broadcast domain.

## Cash this week vs replacement

| Line | Cash this week | Replacement street |
| --- | --- | --- |
| Hardware in the rack | **$27.99** (switch only, if both laptops and the gateway are already in the house) | ~$910–990 |
| Recurring WAN | carrier plan | see below |

Target for a viewer starting from zero hardware, laptops included: **under $1,000** before tax and before the monthly radio bill.

## Hardware

| Qty | Item | Role | Street (this date) | Line | Notes |
| --- | --- | --- | --- | --- | --- |
| 1 | AT&T / T-Mobile / Verizon home internet gateway | WAN + default LAN (+ their guest Wi-Fi if you leave it on) | $0 hardware with plan | $0 | Included brick. Does **not** speak 802.1Q trunks. Bridge / passthrough if the model has it. CGNAT is likely. |
| 1 | TP-Link TL-SG108E (8-port Gigabit Easy Smart) | VLAN brain | **$27.99** (your cart) / $29.99 Amazon list the same day | $27.99 | 802.1Q and port-based VLAN. This is the stick. [Amazon](https://www.amazon.com/TP-LINK-TL-SG108E-8-Port-Gigabit-Tag-Based/dp/B00K4DS5KU/) |
| 1 | Lenovo ThinkPad, AMD Ryzen 5 7535U, 16 GB RAM | VLAN 10 trusted | already owned — replacement used ~$550–600 | $0 cash / ~$575 replace | 64-bit, no touch. Treat as E16/L16-class. RJ45 if the chassis has it; USB-C NIC if not. |
| 1 | ACEMAGIC / Mallrace-class AX17 Pro, R3-4300U, 16 GB / 512 GB | VLAN 20 guest / wasp box | ~$309 sale (maker) / $260–400 street | $0 cash if owned / ~$309 replace | The loud laptop. Guest endpoint. |

**Hardware subtotal (cash, gear you listed as on-hand except calling out the switch):** $27.99  
**Hardware subtotal (replace all silicon, gateway still bundled):** ~$912 + tax

## Recurring

| Item | Role | Typical | Notes |
| --- | --- | --- | --- |
| Home internet plan (ATT / T-Mo / VZ) | WAN | ~$50–70 / mo | Price the plan you actually sit on. Radio + CGNAT + whoever's app. |

## Port map (TL-SG108E)

| Port | VLAN | What plugs in |
| --- | --- | --- |
| 1 | trunk or untagged to gateway LAN | ISP box LAN Ethernet |
| 2 | 10 access | ThinkPad |
| 3 | 20 access | AX17 Pro |
| 4–8 | unused / future AP / camera | off or dead VLAN until an episode needs them |

Mgmt of the switch: from the ThinkPad. No third laptop. VLAN 99 can wait until we have a reason.

## What this fabric can do

- Split trusted and guest at L2 on a $28 switch.
- Show two hostnames, two MACs, two ports.
- Make “guest should not see trusted” a screenshot.

## What this fabric cannot do (yet)

- Classic RoS subinterfaces on the carrier box. That box is a NAT gateway.
- Clean inter-VLAN routing with inspection. Hairpin, if it happens, is through the ISP LAN — which is why isolation on the SG108E matters.
- A third mgmt plane. Two laptops. Do not invent a jump box.

## Substitutions

- Any 8-port Easy Smart that does 802.1Q (TL-SG108E is the priced SKU).
- Any ThinkPad-class 16 GB AMD/Intel used box if the 7535U walks.
- Any $300-ish 16/512 beater for VLAN 20.
- Fiber ONT + your own router is a *later* topology. Do not sneak it into 01.

## What we refused to buy

- L3 switch as the brain.
- A firewall appliance for episode 1.
- A third laptop just to have VLAN 99 on camera.
- New retail ThinkPad pricing.
