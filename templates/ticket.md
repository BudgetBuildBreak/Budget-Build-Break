# Ticket — ALERT / CASE NAME

Builders show racks. Analysts show tickets. Fill this on every C episode.

- **Case ID:** TOPOLOGY-EP (example: 01-1C)
- **Opened:** YYYY-MM-DD
- **Analyst:**
- **Alert name / source / severity:**
- **Asset:** hostname / IP / user / VLAN
- **Status:** open | contained | closed-TP | closed-FP | closed-suspicious

## First five questions

1. What fired, and on which box?
2. What was the parent process / auth event / radio client?
3. Where did it go next (host, identity, net)?
4. Is this expected on *this* fabric today?
5. Who else would see this if we were on shift?

## Evidence pulled

| Source | What we pulled | Result |
| --- | --- | --- |
| Host / EDR-ish (Wazuh, Sysmon, process) | | |
| Network (switch mirror, firewall, DNS) | | |
| Identity (local account, MDM, IdP) | | |
| Email / user report | | |

Minimum: one host or identity row **and** one network row.

## Decision

- [ ] True positive
- [ ] False positive
- [ ] Suspicious / needs watch

Why, in two sentences:

## Containment (or why not)

What we changed on *this* lab. If we did not contain, say why.

## Detection gap

What should have fired and did not.

## Six-sentence handoff

1.
2.
3.
4.
5.
6.

Link: detections file · AAR · video
