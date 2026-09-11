# IR playbook — Topology 01 RoS

Civilian loop. Same words every episode.

## Triage

- Is VLAN 10 still talking to the gateway?
- Is VLAN 99 still reachable from a mgmt port only?
- What extra client, lease, or MAC showed up on 20?
- Is the trunk still a trunk?

## Contain

- Pull guest ports to a dead VLAN or shut them if the lab is small enough to be honest.
- Stop NAT for VLAN 20 if it was on.
- Do not debug from a trusted desktop while guest is on fire.

## Eradicate

- Kill the bad lease / session / cred that the signature pointed at.
- Fix the rule that let 20 talk to 10, if that is what happened.
- Do not call it clean because the toy left the table.

## Rebuild

- Bring VLAN 10 back on purpose.
- Confirm 20 cannot initiate to 10.
- Confirm mgmt is still 99-only.
- Take the “healthy” screenshot that signatures.md is missing.

## Hand off

Write three lines in [lessons.md](lessons.md). If you cannot write three lines, the episode did not finish.
