# Topology 01 — Router-on-a-stick

First fabric. Honest SoHo: one cheap router, one cheap managed switch, three VLANs. Later we break it on purpose. First we build it so the break means something.

Status: planned. Packet Tracer file not in-repo yet.

## Why this piece exists

Cheapest inter-VLAN fabric you can buy this week. Teaches tagged vs access, native VLAN, and which hop is the trust boundary. East-west traffic hairpins through the router. That hairpin is the lesson waiting in the wasp episodes.

## Diagram

```
Internet
    |
 [Budget router]          WAN on one interface
    | 802.1Q trunk        subinterfaces per VLAN
 [Managed switch]
    |-- VLAN 10  Trusted
    |-- VLAN 20  Guest / IoT
    |-- VLAN 99  Mgmt
```

## Addressing (lab defaults — change if they collide with your house)

| VLAN | Name | Net | Gateway |
| --- | --- | --- | --- |
| 10 | Trusted | 10.10.10.0/24 | 10.10.10.1 |
| 20 | Guest / IoT | 10.10.20.0/24 | 10.10.20.1 |
| 99 | Mgmt | 10.10.99.0/24 | 10.10.99.1 |

NAT overload on WAN for VLAN 10 first. Guest does not get out until an episode says it does. Mgmt only from VLAN 99.

## Packet Tracer checklist

- Router: WAN toward cloud. Other interface is the trunk.
- Subinterfaces `.10` `.20` `.99` with the gateways above.
- Switch: one trunk uplink. Access ports: one trusted, one guest, one mgmt.
- Three endpoints, one per VLAN, default gateways on the stick.
- A short filter: VLAN 20 does not initiate to VLAN 10.

Drop the `.pkt` at `assets/topology-01-ros.pkt` and link it here.

## Series on this fabric

See [series-map.md](../../series-map.md). Willy, Wanda, then Leroy, then the household night. Same stick. Different weather.

## Cookbook pages

- [BOM](bom.md)
- [Signatures](signatures.md)
- [IR playbook](ir-playbook.md)
- [Lessons](lessons.md)
