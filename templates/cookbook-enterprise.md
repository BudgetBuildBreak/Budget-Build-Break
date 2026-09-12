# Runbook — [SERVICE / TOPOLOGY / CONTROL]

| Field | Value |
| --- | --- |
| Document ID | BBB-RB-NNN |
| Version | 0.1 |
| Status | Draft \| Review \| Approved |
| Classification | Internal |
| Owner | |
| Technical approver | |
| Review cycle | 90 days or after any Priority-1 incident |
| Last reviewed | YYYY-MM-DD |
| Related topology | 01-ros \| 02-slate-nat \| 03-two-sensors \| 04-mdm \| 05-till |
| Related episode | _C |
| Ticket / change | |

---

## 1. Purpose

One paragraph. What this runbook exists to restore or operate.

## 2. Scope

### In scope

-

### Out of scope

-

## 3. Criticality

| Item | Value |
| --- | --- |
| Business service | |
| Impact if this fails | |
| RTO | |
| RPO | |
| Data class | none \| internal \| PII \| payment |

## 4. Architecture context

| Zone / VLAN | Host | Role |
| --- | --- | --- |
| | | |

Diagram or link: `docs/topologies/NN-name/README.md`

Healthy baseline evidence: link to screenshot / Wazuh filter / Packet Tracer file.

## 5. Preconditions

- [ ] Operator has access to VLAN 99 / jump path
- [ ] Wazuh dashboard reachable
- [ ] Current software-register row is not `unknown`
- [ ] Change window (if required):

## 6. RACI

| Activity | Hive (operator) | Approver | Vendor |
| --- | --- | --- | --- |
| Detect | R | I | I |
| Triage | R | C | I |
| Contain | R | C | I |
| Eradicate | R | A | C |
| Recover | R | A | C |
| Lessons / this doc | R | A | I |

R = responsible, A = accountable, C = consulted, I = informed.

## 7. Detection

| Signal | Where | Healthy | Suspect |
| --- | --- | --- | --- |
| | Wazuh / switch UI / Slate / Spitz | | |

Do not list steps that produce the weather. List how the hive recognizes it.

## 8. Procedure

Numbered. Each step: action, expected result, evidence to capture.

### 8.1 Triage

1. Action:  
   Expected:  
   Evidence:

### 8.2 Contain

1. Action:  
   Expected:  
   Evidence:

### 8.3 Eradicate

1. Action:  
   Expected:  
   Evidence:

### 8.4 Recover

1. Action:  
   Expected:  
   Evidence:

### 8.5 Validate

- [ ] Trusted VLAN 10 reaches the gateway
- [ ] Share (VLAN 30) opens from ThinkPad if this fabric includes it
- [ ] Guest / dirty (20) cannot initiate to 10/30/60
- [ ] Wazuh agents green for hosts in scope
- [ ] Healthy screenshot attached

## 9. Rollback

If recover fails, return to last known good.

1.  
2.  

Abort criteria:

-

## 10. Escalation

| Condition | After | To |
| --- | --- | --- |
| No restore within RTO | | |
| Payment / PII zone touched | | Stop. Topology 05 rules. |
| Hardware DOA | | Amazon RMA — film it |

## 11. Communications

| Audience | When | What |
| --- | --- | --- |
| Hive / comments | After C ships | Signature + this URL |
| Nobody else | — | No real SSIDs, no real neighbors |

## 12. Evidence pack

| Artifact | Location |
| --- | --- |
| Screenshots | `assets/` |
| Wazuh filter / alert IDs | |
| Config diff | |
| BOM line if SKU changed | `docs/topologies/NN/bom.md` |
| Software versions | `docs/topologies/NN/software.md` |

## 13. Metrics

| Metric | Target |
| --- | --- |
| Time to detect | |
| Time to contain | |
| Time to recover | |
| Recurrence | 0 on this fabric before next topology |

## 14. Related documents

- Topology README
- BOM
- Software register
- VLAN plan (`docs/vlan-plan.md`)
- IR playbook in the topology folder
- `templates/cookbook-page.md` (short form for the video close)

## 15. Revision history

| Ver | Date | Author | Change |
| --- | --- | --- | --- |
| 0.1 | YYYY-MM-DD | | Initial |

---

Copy to `docs/topologies/NN-name/runbooks/RB-name.md` when an episode C closes.
