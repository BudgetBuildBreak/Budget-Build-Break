# Topology 01 — Carrier box + smart switch + two laptops

Working title in the repo is still `01-ros` because the *lesson* is the stick: one uplink, tagged or port VLANs, two rooms. The silicon is simpler than a Cisco lab.

Status: BOM filled 2026-09-11. Packet Tracer optional; this one can be a photo of the desk.

## Why this piece exists

You already have internet. You already have two PCs. Twenty-eight dollars buys a switch that can lie about being one house. That is the most honest SoHo start.

## Diagram

```
[ ATT / T-Mobile / Verizon home internet box ]
                 |
                 |  LAN Ethernet (untagged to the carrier)
                 v
        [ TP-Link TL-SG108E ]
           |              |
     VLAN 10 access   VLAN 20 access
           |              |
     ThinkPad 7535U   AX17 Pro 4300U
     trusted          guest / wasp box
```

## Addressing

Let the carrier box keep DHCP until an episode takes it away.

| Role | Device | How it gets an address |
| --- | --- | --- |
| WAN + default LAN | ISP gateway | carrier |
| Trusted | ThinkPad | DHCP from gateway *or* static on the VLAN 10 port once we lock the switch |
| Guest | AX17 Pro | DHCP on VLAN 20 only |

Do not pretend the ISP box is `10.10.10.1` until we measure what it actually hands out. Write the real lease here after first boot.

## BOM

Priced [bom.md](bom.md). Cash-this-week if the PCs and radio are already in the house: **$27.99** for the TL-SG108E.

## Cookbook pages

- [Signatures](signatures.md)
- [IR playbook](ir-playbook.md)
- [Lessons](lessons.md)
