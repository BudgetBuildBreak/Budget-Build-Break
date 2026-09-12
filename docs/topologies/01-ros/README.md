# Topology 01 — Carrier box, switch, two laptops

Three episodes. Then we leave this fabric on purpose.

- ThinkPad = host user (VLAN / port 2)
- AX17 Pro = Wazuh on Parrot, USB NIC on the SG108E span (port 3)
- ISP gateway = start, not home

## Trilogy

**1A Budget.** The two laptops are already on the desk — still walk the specs and the used-vs-new number so bees can copy the buy. Why TL-SG108E at $28. Why a carrier home box is episode 1 and not episode 12.

**1B Harden.** Fresh images. Firewall on the ThinkPad. Parrot on the AX17. Switch VLANs + mirror. Packets into Wazuh. Screenshot of healthy.

**1C Weather + IR.** Willy's first walk-on. Show why this security is thin *here*. Then triage, contain, eradicate, lessons learned. Those lessons are why 02 exists.

## Diagram

```
[ ATT / T-Mobile / Verizon home internet box ]
                 |
                 |  port 1
                 v
        [ TP-Link TL-SG108E ]
           |              |
        port 2          port 3  (mirror dest)
           |              |
      ThinkPad         AX17 Pro + $10 USB NIC
      host user        Parrot + Wazuh
                         |
                      Wi-Fi to gateway (mgmt)
```

## Cookbook

- [BOM](bom.md)
- [Signatures](signatures.md)
- [IR playbook](ir-playbook.md)
- [Lessons](lessons.md)
