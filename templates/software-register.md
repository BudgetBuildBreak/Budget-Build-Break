# Software register — TOPOLOGY NN

Date checked: YYYY-MM-DD
Who checked:

Track what is running, what channel it updates from, and whether this week is current. This is not a CVE blog. It is a list Wazuh and the hive can agree on.

Status: `current` | `behind` | `pinned` | `unpatchable` | `unknown`

`unpatchable` = we do not control the vendor (carrier gateway). Compensating control lives in the topology README, not in a hope.

## Inventory

| Host | Role | OS / firmware | Version now | Update channel | Last patched | Status | Notes |
| --- | --- | --- | --- | --- | --- | --- | --- |
| | | | | | YYYY-MM-DD | | |

## Apps that matter

Only what can change the fabric or the evidence. Not every store app.

| Host | App | Version now | Update channel | Last patched | Status | Why it matters |
| --- | --- | --- | --- | --- | --- | --- |
| | | | | | | |

## Identification (how we know)

| Host | How we read version | How we hear about patches |
| --- | --- | --- |
| | | |

Examples: `winver` / Settings → Windows Update; `winget list`; Parrot `apt policy`; Slate UI → firmware; G11 BIOS splash; Wazuh agent → Vulnerability Detection inventory.

## Behind this week

| Host | What | Risk on *this* fabric | Action |
| --- | --- | --- | --- |
| | | | |

## Pinned on purpose

| Host | What | Why we will not bump |
| --- | --- | --- |
| | | |

Copy to `docs/topologies/NN-name/software.md`.
