# Topology 03 — two visibility points

Mitigation of 02C. Same silicon as 02. New job: a packet tap that is not the dashboard.

## Why this fabric exists

One feed lies when it is new. Wazuh on the AX will miss toy-class weather if alerts are not tuned. A second point on the G11 span does not make us clever. It makes a miss expensive for Leroy instead of free.

Willy can still be loud on 01/02. Leroy is why we wait until the house exists before we add the tap — toys show up as odd clients and odd frames, not as a textbook scan.

## Trilogy

**3A Budget.** No new box unless 02C forced one. Cost is time: VM, span cable, decoder.

**3B Harden.** G11 NIC2 = SG108E mirror dest. IDS in a VM. Alerts into Wazuh. Tune until the two feeds argue in public.

**3C Weather + IR.** Leroy. Show one point quiet and the other loud, or both loud. IR close. Cookbook gets the tell.

## Diagram

```
AX17     Wazuh          visibility point 1  (host / log / agent)
G11 VM   packet IDS     visibility point 2  (span on NIC2)
              \
               → alerts into Wazuh (one console)
```

Do not inline the NAS. Span only. See the 02 note that reserved NIC2.

## Cookbook

- [BOM](bom.md)
- [lessons.md](lessons.md) — fill after 3C
