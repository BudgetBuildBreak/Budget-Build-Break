# Software register — Topology 02

Date checked: 2026-09-11
Who checked: draft — fill at 2B

## Inventory

| Host | Role | OS / firmware | Version now | Update channel | Last patched | Status | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- |
| ISP gateway | NAT #1 | Vendor firmware | unknown | carrier | | unpatchable | Still untrusted. |
| Slate AX GL-AXT1800 | NAT #2 | OpenWrt / GL firmware | unknown | GL.iNet / opkg | | unknown | First box we patch. |
| GMKtec G11 hypervisor | NAS host | TBD (2B) | unknown | vendor + OS | | unknown | Dual NIC. |
| G11 VM | Packet IDS | TBD guest | unknown | guest + rule pack | | pinned | Not in 1B. Span only. Feeds Wazuh. |
| TL-SG108E | Switch | Easy Smart firmware | unknown | TP-Link | | unknown | |
| ThinkPad | User | Windows 11 | unknown | Windows Update | | unknown | |
| AX17 | Wazuh | Parrot OS | unknown | Parrot repos | | unknown | No Snort here. |

## Apps that matter

| Host | App | Version now | Update channel | Status | Why it matters |
| --- | --- | --- | --- | --- | --- |
| Slate | GL UI | TBD | GL firmware | unknown | Office SSID |
| G11 host | file share | TBD | OS | unknown | Honey on disk |
| G11 VM | Snort or Suricata | TBD | distro + rules | pinned | Packet tell → Wazuh |
| AX17 | Wazuh | TBD | Wazuh packages | unknown | Only dashboard |

## Identification

| Host | How we read version | How we hear about patches |
| --- | --- | --- |
| Slate | Admin → Upgrade | GL release notes |
| G11 host | OS about + BIOS | vendor + OS |
| G11 IDS VM | engine `-V` / package | rule-pack date in the VM |
| AX17 | `apt policy wazuh-manager` | Wazuh releases |
| All agents | Wazuh inventory | dashboard vs this table |

See [ids.md](ids.md) for placement.
