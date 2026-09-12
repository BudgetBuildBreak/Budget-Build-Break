# VLAN plan

After topology 04 the paint lives on the **Spitz**. The blast bridge still denies. The SG108E still tags ports. The Slate is only the dirty AP.

| ID | Zone | Hosts | First topology |
| --- | --- | --- | --- |
| 1 | unused | nothing | — |
| 10 | Trusted | ThinkPad | 01 |
| 20 | Dirty | Slate AP: IoT, guests, printers | 04 (Slate demoted) |
| 30 | Servers | G11 NAS | 02 |
| 40 | Chair | Pi | 03 |
| 50 | Phones | prepaid Androids, MDM | 04 |
| 60 | Money | till | 05 |
| 99 | Mgmt | Spitz / Slate / SG108E / path PC UIs | 02–04 |

## Allows

- 10 → 30 (share)
- 10 → internet
- 50 → internet + MDM only
- 20 → internet only
- 40 → internet only; never 10/30/60
- 60 → internet only; never 20/40; never 10 except a filmed jump
- 99 → from 10 only

## Radios after 04

| Radio | SSID job | VLAN |
| --- | --- | --- |
| Spitz | Office | 10 / 50 |
| Slate | Dirty | 20 |
| Carrier gateway | Shelf | — |
