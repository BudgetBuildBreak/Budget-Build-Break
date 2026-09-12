# Detections — 01 Desk

| # | Name | Source | Host / identity / net | What success looks like | Fired? | Tune next |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | New / unexpected process on ThinkPad | Wazuh agent | host | Alert + process tree | TBD | |
| 2 | Local failed or unexpected logon | Windows / auth log via Wazuh | identity | Event + user + source | TBD | |
| 3 | New MAC or talker on span | Switch mirror / Wazuh network | net | MAC / IP that is not the desk kit | TBD | |

Packet-only tables fail this episode. Rows 1 or 2 must get a screenshot.

## Rule notes

Paste the actual Wazuh rule ID or Event ID after 1B.

## Screenshots / exports

`assets/topology-01-ros-sig-*.png`
