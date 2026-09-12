# Packet IDS — G11 VM, not the AX

Decision: **Snort (or Suricata) lives in a VM on the GMKtec G11.** The AX17 stays Parrot + Wazuh. Do not put a second brain on the 4300U.

## Why the mini PC

- Two 2.5G ports. One for the house, one for the copy.
- NAS already sits on the inside LAN. The tap should sit next to the files, not next to the dashboard.
- If the VM wedges, Wazuh on the AX still answers. If Snort had been on the AX, you lose evidence and the sensor together.

## Why a VM

- Snapshot before a rule pack eats the box.
- Cap CPU so the share still opens from the ThinkPad.
- Throw the VM away without reimaging the NAS.

## Cable

| G11 NIC | Job |
| --- | --- |
| 2.5G #1 | Slate LAN — NAS + VM management |
| 2.5G #2 | SG108E mirror destination — IDS only, no default route |

Do **not** bridge the NAS through the IDS VM. Inline is how you turn a file server into an outage. Span only.

SG108E: keep port 3 as the span dest if it still faces the G11 sniff NIC. Move the AX off that port; AX talks to Slate LAN 2 for Wazuh only.

## Data flow

```
ThinkPad / G11 share  →  SG108E  →  mirror  →  G11 NIC2  →  IDS VM  →  alerts  →  Wazuh on AX17
```

One console on camera: Wazuh. The VM has a CLI and a log file. That is enough.

## When it ships

| Episode | IDS |
| --- | --- |
| 1A / 1B / 1C | No. No G11 yet. |
| 2A | Buy / unbox only. Mention the second NIC. |
| 2B | Optional: VM created, no rule drama. |
| 2C | Alerts in Wazuh if 2B left it running. |

## Software row

See [software.md](software.md). Status starts `pinned` until 2B images the VM.
