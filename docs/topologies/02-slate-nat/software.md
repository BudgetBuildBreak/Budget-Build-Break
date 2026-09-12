# Software register — Topology 02

Date checked: 2026-09-11
Who checked: draft — fill at 2B

Carries 01 hosts. New brain and disk.

## Inventory

| Host | Role | OS / firmware | Version now | Update channel | Last patched | Status | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- |
| ISP gateway | NAT #1 | Vendor firmware | unknown | carrier | | unpatchable | Still untrusted. |
| Slate AX GL-AXT1800 | NAT #2 | OpenWrt / GL firmware | unknown | GL.iNet firmware / opkg | | unknown | First box we patch on purpose. |
| GMKtec G11 | NAS | Windows or Linux (pick in 2B) | unknown | vendor + OS updates | | unknown | Dual NIC firmware too. |
| TL-SG108E | Switch | Easy Smart firmware | unknown | TP-Link | | unknown | |
| ThinkPad | User | Windows 11 | unknown | Windows Update | | unknown | |
| AX17 | Wazuh | Parrot OS | unknown | Parrot repos | | unknown | |

## Apps that matter

| Host | App | Version now | Update channel | Status | Why it matters |
| --- | --- | --- | --- | --- | --- |
| Slate | GL UI / VPN stack if enabled | TBD | GL firmware | unknown | Office SSID lives here |
| G11 | file share (SMB / whatever 2B picks) | TBD | OS | unknown | Honey on disk |
| AX17 | Wazuh | TBD | Wazuh packages | unknown | Still the evidence plane |

## Identification

| Host | How we read version | How we hear about patches |
| --- | --- | --- |
| Slate | Admin → Upgrade / `cat /etc/openwrt_release` | GL.iNet release notes |
| G11 | OS about + BIOS | vendor + OS |
| All agents | Wazuh Vulnerability Detection / syscollector | dashboard vs this table |

## Behind this week

Fill after 2B first boot. If Wazuh says behind and this table says current, the table is wrong.
