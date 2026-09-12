# BOM — Topology 02

Date priced: 2026-09-11
Currency: USD

Carries forward [01-ros](../01-ros/bom.md). New spend: Slate AX + GMKtec G11. Amazon is the vendor on purpose. If it dies, that is an episode, not an apology. Return it. Buy the next one. Budget first means you accept the lottery.

## Already in the house (01)

| Item | Role | Cash already spent |
| --- | --- | --- |
| ISP gateway | NAT #1 | $0 hardware |
| TL-SG108E | Inside switch | $27.99 |
| ThinkPad 7535U | User | owned |
| AX17 Pro + USB NIC | Wazuh | owned + $9.99 |

## New this episode

| Qty | Item | Role | Street (this date) | Cash | Notes |
| --- | --- | --- | --- | --- | --- |
| 1 | GL.iNet GL-AXT1800 Slate AX | NAT #2 | **$119** | $119 | WAN + two LAN. Port 2 = AX17. Wi-Fi 6 travel box. OpenWrt. Amazon / GL store. |
| 1 | GMKtec G11 mini PC — Ryzen Embedded R2514, 16 GB DDR4, 256 GB NVMe, dual 2.5G, Wi-Fi 6E | NAS / file server | **$309.99** | $309.99 | Beats a 4300U/N150 on paper. Two RJ45 so the share can stay wired. Amazon's Choice. 4.2 stars — that decimal is the plot. |

**Cash this episode:** $428.99 + tax  
**Cash so far (01+02 new silicon):** $466.97  
**Replace-all (laptops + these + switch + dongle):** ~$1,350 before the radio bill

## Recurring

Same carrier plan as 01. Slate does not add a subscription.

## Port map

### Slate AX

| Port | Job |
| --- | --- |
| WAN | Carrier LAN (NAT #1 → NAT #2) |
| LAN 1 | Uplink to TL-SG108E |
| LAN 2 | AX17 Wazuh (mgmt + optional span later) |

### TL-SG108E

| Port | Job |
| --- | --- |
| 1 | Slate LAN 1 |
| 2 | ThinkPad |
| 3 | G11 NAS |
| 4–8 | Dark |

G11 has two 2.5G ports. Use one. Park the second until an episode needs a second path.

## Amazon lottery (channel rule)

We bought these here so a DOA or a two-month death is filmable. Receipt, RMA, replacement SKU, what Wazuh saw when the box went dark. Do not hide it. Do not pretend enterprise gear would have saved a $310 mini PC.

## What we refused to buy

- Slate 7 Pro at $240 for two extra radios we do not need on day two.
- A 4-bay NAS.
- A second switch.
- Extended warranty as the plan. The plan is the return window.
