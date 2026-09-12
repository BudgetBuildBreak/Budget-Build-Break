# Lab ground rules

Working notes. Change them when the lab changes.

## Design rules

- Every box has a job you can say in one sentence.
- If two boxes do the same job, one of them is gone.
- Guest / IoT never share a broadcast domain with trusted clients.
- Admin interfaces are not on the same VLAN as the living-room TV.
- Backups are not “a disk in the same rack as the server.”

## Budget rules

- Price at time of build lives in the BOM. Do not pretend last year's prices still hold.
- Prefer used / refurb when the failure mode is understood.
- Power and noise count as budget. A cheap box that needs a new circuit is not cheap.
- Write the cut. If you skipped a sensor to hit the cap, say what you are now blind to.

## Break rules

- We break *this* build. Not a hypothetical enterprise.
- Show the signature (log line, packet, dashboard), not just the tool name.
- Every C episode fills `ticket.md` then `detections.md` then `aar.md`.
- Every C episode produces at least one host or identity IoC **and** one network IoC.
- Weather is fiction. No real apartments, no real SSIDs, no real faces.
- Wasps get a price *class* for the object. Not a haul. Not a starter kit.
- The cookbook is triage → eradicate → rebuild → lessons. Not how to be the wasp.
- If the control failed, say so. The next video is allowed to fix it.
- Yellowjackets do not ship until money moves and PII exists on the lab.
- Next fabric stays locked until this fabric has a closed AAR.

## Secrets

- No live API keys, tokens, real SSIDs, phone numbers, or customer PII in this repo.
- Config samples are redacted. Use `.env.example`, never `.env`.
