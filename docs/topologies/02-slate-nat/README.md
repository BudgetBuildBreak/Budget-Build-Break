# Topology 02 — Slate AX double NAT + GMKtec G11 NAS

Mitigation of 01C. Trilogy: budget, harden, weather + IR.

SKU lock: **GL.iNet GL-AXT1800 Slate AX** ($119) and **GMKtec G11** ($309.99).

Packet IDS: **not this fabric.** Second 2.5G NIC exists so topology 03 has a tap. Do not stand up the VM in 2B just because the port is there.

## Why this fabric exists

01 lived on a box we do not control. 02 puts a brain we configure in front of the files. Slate Wi-Fi is the first office SSID. Carrier SSID gets parked. Double NAT is named, not hidden.

## Trilogy

**2A Budget.** Slate vs the brick. G11 vs files on a laptop. Dual NIC is a promise, not an episode.

**2B Harden.** Slate WAN into the carrier. AX17 on Slate LAN 2. SG108E on LAN 1. ThinkPad + G11 NIC1 on the switch. Office SSID. Share a folder. Wazuh only.

**2C Weather + IR.** One dashboard. If that is not enough, that sentence is the cold open for 03.

## Diagram

```
[ ISP home internet box ]                      NAT #1  (untrusted)
         |
         v
[ Slate AX WAN ]
[ Slate AX LAN ]                               NAT #2  (ours)
    |            |
  LAN 2        LAN 1
    |            |
 AX17 Pro    [ TL-SG108E ]
 Wazuh only      |
             ----+----
             |       |
        ThinkPad   G11 NIC1 NAS
        host user  NIC2 dark → topology 03
```

## Cookbook

- [BOM](bom.md)
- [IDS deferred](ids.md)
- [Software / patch register](software.md)
- [Signatures](signatures.md)
- [IR playbook](ir-playbook.md)
- [Lessons](lessons.md)
