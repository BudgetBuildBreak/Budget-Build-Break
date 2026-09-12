# Threat model — 01 Desk

Scope: this topology only. Not a generic CISSP essay.

## Assets that matter here

| Asset | Why it matters on this build |
| --- | --- |
| ThinkPad user session | Only real workstation. Compromising it is the office. |
| Wazuh on AX17 | Only visibility. If it is blind, the episode is blind. |
| SG108E mgmt / mirror | Cheap switch. Mis-VLAN or open mgmt is the own-goal. |
| Carrier gateway | Landlord radio. We do not own it. Assume it is sloppy. |

## Trust boundaries

- Internet ↔ carrier box
- Carrier box ↔ SG108E port 1
- Port 2 user ↔ port 3 sensor
- Guest / IoT (when named) ↔ trusted port
- Admin plane (switch UI, Wazuh) ↔ living-room Wi-Fi

## Relevant threats (ranked for this fabric)

| # | Threat | Why it is realistic here | Signature we should see | Control that actually fits the budget |
| --- | --- | --- | --- | --- |
| 1 | Walk-on client on the wrong VLAN | Desk switch, default-ish carrier Wi-Fi | New MAC / DHCP / Wazuh agent or auth noise | VLAN + mirror + “who just joined” |
| 2 | User laptop runs unexpected process after a click | Only host we have | Wazuh FIM / process / Sysmon-style log | Host firewall + Wazuh agent on ThinkPad |
| 3 | Mgmt UI reachable from the wrong zone | $28 switch, habit | Hit on switch IP from VLAN that should not | Mgmt ACL / unplug the habit |

## Out of scope (and why)

Ransomware crew against a till. There is no till yet. Nation-state. There is no prize.

## Break plan

1C: Willy on *this* trunk. Success = a ticket with evidence from Wazuh **and** the span, not a vibe.
