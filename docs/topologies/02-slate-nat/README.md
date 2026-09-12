# Topology 02 — Slate AX double NAT + GMKtec G11 NAS

Mitigation of 01C. Trilogy: budget, harden, weather + IR.

SKU lock: **GL.iNet GL-AXT1800 Slate AX** ($119) and **GMKtec G11** ($309.99).

Packet IDS: **VM on the G11**, second 2.5G NIC on the span. AX17 stays Wazuh only. Details in [ids.md](ids.md).

## Why this fabric exists

01 lived on a box we do not control. 02 puts a brain we configure in front of the files. Slate Wi-Fi is the first office SSID. Carrier SSID gets parked. Double NAT is named, not hidden.

## Trilogy

**2A Budget.** Slate vs staying on the brick. G11 vs “files on a laptop.” Second NIC is why the G11 wins over a one-port N150. Amazon lottery is the warranty.

**2B Harden.** Slate WAN into the carrier. AX17 on Slate LAN 2. SG108E on LAN 1. ThinkPad + G11 on the switch. Office SSID on the Slate. Share a folder. Optional: IDS VM up, empty / quiet.

**2C Weather + IR.** Wasp on the new house. Wazuh is the console. IDS alerts only if they feed it.

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
             ----+----+-------------
             |        |            |
        ThinkPad   G11 NIC1     G11 NIC2 (span dest)
        host user  NAS host     IDS VM
```

## Cookbook

- [BOM](bom.md)
- [IDS placement](ids.md)
- [Software / patch register](software.md)
- [Signatures](signatures.md)
- [IR playbook](ir-playbook.md)
- [Lessons](lessons.md)
