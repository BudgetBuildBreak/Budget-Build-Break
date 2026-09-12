# VLAN plan

Paint on the SG108E. Policy on the Slate (02) then the blast bridge (03+).
Default deny between zones. Allows are the cookbook.

Do not create a VLAN on camera until a device lives in it.

| ID | Zone | Hosts | First topology |
| --- | --- | --- | --- |
| 1 | unused | nothing | — |
| 10 | Trusted | ThinkPad | 01 |
| 20 | Guest / dirty | parked carrier SSID, visitors | 02 |
| 30 | Servers | G11 NAS; path-PC mgmt if split | 02–03 |
| 40 | Chair | Pi honeynet | 03 |
| 50 | Phones | prepaid Androids + MDM reachability | 04 |
| 60 | Money | Mac mini till | 05 |
| 99 | Mgmt | Slate / SG108E / bridge UIs | 02–03 |

## Allows we will say out loud

- 10 → 30 (map the share)
- 10 → internet
- 50 → internet + MDM box only
- 20 → internet only
- 40 → internet only; never 10/30/60
- 60 → internet only (banks); never 20/40; never 10 except a filmed jump
- 99 → from 10 only

## Where tags happen

| Fabric | Mechanism |
| --- | --- |
| 01 | Access ports on SG108E. Carrier is not a trunk. |
| 02 | Slate SSID → VLAN. Guest isolation on. |
| 03+ | Bridge NIC B is the 802.1Q trunk into the SG108E. |

VLANs without deny rules are paint. See episode machine C for proving a pin-hole.
