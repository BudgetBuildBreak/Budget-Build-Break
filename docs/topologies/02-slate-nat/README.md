# Topology 02 — Slate AX double NAT + GMKtec G11 NAS

Episode 2. Intro taught the rhythm. This is the first house.

SKU lock: **GL.iNet GL-AXT1800 Slate AX** ($119) and **GMKtec G11** ($309.99). Both Amazon. If they fail, that is seasoning.

## Why this piece exists

Carrier box stays dumb. Slate is the first brain we configure. G11 is the first disk that matters. Double NAT is drawn, named, and left in place.

## Diagram

```
[ ATT / T-Mobile / Verizon home internet box ]     NAT #1
                      |
                      v
              [ Slate AX WAN ]
              [ Slate AX LAN ]                     NAT #2
                 |           |
              LAN 2       LAN 1
                 |           |
            AX17 Pro      [ TL-SG108E ]
            Wazuh            |
                         ----+----
                         |       |
                    ThinkPad   GMKtec G11
                    host user  NAS / files
```

## Roles

| Device | Job |
| --- | --- |
| ISP gateway | Radio. NAT #1. |
| Slate AX | NAT #2. First box we configure. |
| AX17 + $10 NIC | Wazuh on Slate LAN 2 |
| TL-SG108E | Inside switch |
| ThinkPad | Host user |
| GMKtec G11 | NAS / file server |

## Addressing (fill after first boot)

| Hop | Typical until measured |
| --- | --- |
| Slate WAN | RFC1918 from the carrier |
| Slate LAN | often 192.168.8.0/24 |
| ThinkPad / G11 | DHCP from Slate, then pin the NAS |

Traceroute from the ThinkPad should show two private hops. That shot is the episode.

## Episode shape

1. Slate WAN into the carrier.
2. AX17 on Slate LAN 2.
3. SG108E on Slate LAN 1.
4. ThinkPad + G11 on the switch.
5. Traceroute. Two NATs. Named.
6. Share a folder on the G11. ThinkPad opens it. Wazuh notes the talk.

## Cookbook

- [BOM](bom.md)
- [Signatures](signatures.md)
- [IR playbook](ir-playbook.md)
- [Lessons](lessons.md)
