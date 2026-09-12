# Software register — Topology 01

Date checked: 2026-09-11
Who checked: draft — fill versions at first boot of 1B

## Inventory

| Host | Role | OS / firmware | Version now | Update channel | Last patched | Status | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- |
| ISP gateway | NAT #1 / radio | Vendor firmware | unknown | carrier / app only | | unpatchable | We do not control this. Do not pretend we do. |
| TL-SG108E | Switch | Easy Smart firmware | unknown | TP-Link utility / web | | unknown | Check before 1B. |
| ThinkPad | Host user | Windows 11 (confirm) | unknown | Windows Update | | unknown | Firewall on in 1B. |
| AX17 Pro | Wazuh | Parrot OS (planned 1B) | unknown | Parrot repos | | unknown | Fresh image in 1B. |
| AX17 USB NIC | Span | Vendor driver | unknown | Windows/Linux package | | unknown | |

## Apps that matter

| Host | App | Version now | Update channel | Last patched | Status | Why it matters |
| --- | --- | --- | --- | --- | --- | --- |
| AX17 | Wazuh agent / manager | TBD | Wazuh packages | | unknown | Evidence plane |
| AX17 | Parrot tools we actually enable | TBD | apt | | unknown | List only what 1B turns on |
| ThinkPad | Windows Defender / firewall | TBD | Windows Update | | unknown | 1B harden |

## Identification

| Host | How we read version | How we hear about patches |
| --- | --- | --- |
| ThinkPad | winver, Settings → Update, winget list | Windows Update + Wazuh syscollector |
| AX17 Parrot | `cat /etc/os-release`, `apt policy wazuh-manager` | Parrot + Wazuh release notes |
| SG108E | web UI footer / Easy Smart utility | TP-Link firmware page |
| ISP box | sticker + admin page | never ours |

## Behind this week

| Host | What | Risk on *this* fabric | Action |
| --- | --- | --- | --- |
| all | versions blank | we cannot claim harden | fill during 1B |
