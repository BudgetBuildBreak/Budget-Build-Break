# Topology 01 — Carrier box, switch, user, Wazuh on a span

Folder name is still `01-ros`. Lesson is still the stick. Roles as of 2026-09-11:

- ThinkPad = host user (VLAN 10)
- AX17 Pro = Wazuh, USB NIC on the SG108E mirror port

Status: BOM filled. First episodes are cable + switch UI + a quiet dashboard.

## Why this piece exists

Absolute basics. Internet you already pay for. Two laptops you already own. A $28 switch that can copy a port. A $10 dongle because the sensor has no RJ45. Build from here.

## Diagram

```
[ ATT / T-Mobile / Verizon home internet box ]
                 |
                 |  port 1
                 v
        [ TP-Link TL-SG108E ]
           |              |
        port 2          port 3  (mirror dest)
        VLAN 10         span
           |              |
      ThinkPad         AX17 Pro + $10 USB NIC
      host user        Wazuh
                         |
                      Wi-Fi to gateway (mgmt only)
```

## Addressing

Write real leases after first boot. Do not invent 10.10.10.0 until the carrier agrees.

| Role | Device | Path |
| --- | --- | --- |
| User | ThinkPad | DHCP on port 2 |
| Sensor mgmt | AX17 | Carrier Wi-Fi |
| Sensor sniff | AX17 USB NIC | no address required on the span |
| Switch UI | SG108E | from the ThinkPad |

## BOM

[bom.md](bom.md) — cash this week **$37.98** (switch + dongle).

## Cookbook

- [Signatures](signatures.md)
- [IR playbook](ir-playbook.md)
- [Lessons](lessons.md)
