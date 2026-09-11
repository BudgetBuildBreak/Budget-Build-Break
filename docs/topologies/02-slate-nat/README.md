# Topology 02 — Slate double NAT + NAS

Episode 2. Intro (01) taught the rhythm: cable, switch UI, quiet dashboard. This episode adds a router you control and a disk that matters.

## Why this piece exists

The carrier box will not be the brain. A GL.iNet Slate sits behind it on purpose. That is double NAT. We do not apologize for it on day two. We draw it, we name both gateways, we show what a file server looks like on the inside LAN.

## Diagram

```
[ ATT / T-Mobile / Verizon home internet box ]     NAT #1
                      |
                      | Ethernet
                      v
              [ Slate WAN ]
              [ Slate LAN ]                        NAT #2
                 |           |
              port 2       other LAN / uplink
                 |           |
            AX17 Pro      [ TL-SG108E ]
            Wazuh            |
                         ----+----
                         |       |
                    ThinkPad   Mini PC
                    host user  NAS / files
```

If the Slate only has **one** LAN port (Slate 7 / Slate 7 Pro): that port goes to the SG108E, and AX17 hangs off a switch port instead of Slate port 2. Say which SKU you have before we film the insert shot.

Slate AX (GL-AXT1800) has WAN + two LAN — port 2 to AX fits that box.

## Roles

| Device | Job |
| --- | --- |
| ISP gateway | Radio. NAT #1. Leave it dumb. |
| Slate | NAT #2. First box we actually configure. |
| AX17 + $10 NIC | Wazuh. Prefer Slate LAN port 2, span still on the SG108E if we keep mirroring the user. |
| TL-SG108E | Inside switch |
| ThinkPad | Host user |
| Mini PC | NAS / file server |

## Addressing (fill after first boot)

| Hop | Typical until measured |
| --- | --- |
| ISP LAN | whatever the carrier hands the Slate WAN |
| Slate LAN | often 192.168.8.0/24 on GL.iNet — confirm |
| ThinkPad | DHCP from Slate |
| NAS | DHCP then pin a static on the Slate |
| AX17 mgmt | Slate LAN or Slate Wi-Fi |

Write the real leases in this file. Two default gateways on a traceroute is the teaching moment.

## Episode shape

1. Plug Slate WAN into the carrier LAN.
2. AX17 on Slate port 2.
3. SG108E on the remaining Slate LAN (or the only LAN).
4. ThinkPad + mini PC on the switch.
5. Show traceroute: user → Slate → carrier → world.
6. Share a folder on the mini PC. ThinkPad opens it. Wazuh notes the talk.

## Cookbook

- [BOM](bom.md)
- [Signatures](signatures.md)
- [IR playbook](ir-playbook.md)
- [Lessons](lessons.md)
