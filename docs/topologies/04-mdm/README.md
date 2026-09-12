# Topology 04 — Spitz + MDM

Own the air. Own the phones. Money still waits.

**GL.iNet GL-X3000 Spitz AX — $379.99.** T-Mobile SIM moves here. Gateway shelves. Slate AX is no longer the edge. It becomes the dirty AP on VLAN 20 (IoT, visitors, printers).

AX17 = MDM (Headwind for the Android herd; Fleet if the ThinkPad is in scope). VLAN 50. Phones reach MDM + internet. They do not mount the NAS. They are not the till.

Path PC remains Wazuh. Spitz is not the SIEM.

## Diagram

```
[ Spitz AX ]     SIM + office SSID + VLAN brain
    |
    +-- 10  ThinkPad
    +-- 50  prepaid phones → MDM on AX17
    +-- 30  G11
    +-- 99  mgmt
    +-- 40  Pi chair
    +-- 20  Slate (dirty AP: IoT / guest / printers)
    +-- 60  empty until 05
         |
    path PC on the trunk: see + deny
```

## Trilogy

**4A** Budget $380. Why the brick dies. Slate demoted, not dumped. MDM named.
**4B** SIM in. Office SSID on Spitz. Slate on 20. Enroll the herd.
**4C** Weather on our radio. IR close.

## Cookbook

- [BOM](bom.md)
- [lessons.md](lessons.md)
