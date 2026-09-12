# CVSS score card for dummies

CVSS is a report card for a hole in software.

The number is **0 to 10**.
Bigger number = scarier hole **on paper**.
It is not “will this ruin *my* house.” It is “how bad is this kind of hole in a vacuum.”

We still decide if it matters on *this* fabric.

---

## The number

| Score | Words | Kid words |
| --- | --- | --- |
| 0.0 | None | No hole |
| 0.1 – 3.9 | Low | Band-Aid |
| 4.0 – 6.9 | Medium | Worth a look |
| 7.0 – 8.9 | High | Fix soon |
| 9.0 – 10.0 | Critical | Drop the sandwich, look now |

---

## How they pick the number (eight questions)

Think of a locked clubhouse.

| Code | Question | Easy answer |
| --- | --- | --- |
| **AV** Attack Vector | Do they have to sit in the room? | Network = they can yell from the street. Adjacent = they need the driveway (Wi-Fi). Local = they need the chair. Physical = they need the box in their hands. |
| **AC** Attack Complexity | Is it one easy trick or a juggling act? | Low = easy. High = fussy. |
| **PR** Privileges Required | Do they already have a key? | None = stranger. Low = kid key. High = teacher key. |
| **UI** User Interaction | Does someone have to click a dumb thing? | None = no click. Required = someone has to fall for it. |
| **S** Scope | Does the hole in the playhouse also break the school? | Unchanged = just this box. Changed = it jumps the fence. |
| **C** Confidentiality | Can they **read** the diary? | None / Low / High |
| **I** Integrity | Can they **scribble** in the diary? | None / Low / High |
| **A** Availability | Can they **hide** the diary so nobody can play? | None / Low / High |

Street + no key + no click + they can read, scribble, *and* hide the diary = big number.
Need the chair + a teacher key + a click + they can only peek = smaller number.

---

## Score card (print this)

```
Name of hole: ____________________    CVE-________
Box it lives on: ________________  VLAN: ____

CVSS:  ___ / 10     Words:  Low / Medium / High / Critical

Street or chair?   street / driveway / chair / hands
Easy or fussy?     easy / fussy
Need a key?        no / kid key / teacher key
Need a click?      no / yes
Jumps the fence?   no / yes

Can they read it?     no / a little / a lot
Can they change it?   no / a little / a lot
Can they break it?    no / a little / a lot

On OUR house, does this box even exist?
  [ ] no  — ignore the panic
  [ ] yes — what VLAN? ______

Can a wasp reach it from where they stand?
  [ ] no   [ ] yes

Do we patch, pin, or compensate?
  [ ] patch now
  [ ] pin (write why in software.md)
  [ ] compensate (Slate / Spitz / deny rule)
  [ ] unpatchable (carrier brick — do not pretend)

Wazuh see it?  [ ] yes  [ ] no  [ ] not enrolled
```

---

## Three rules so a 10-year-old does not get played

1. **A 9.8 on a program we do not run is a 0 on this desk.**
2. **A 4.3 on the till (VLAN 60) can matter more than a 9.8 on the chair (VLAN 40).**
3. **The number is homework. The VLAN is the test.**

---

## Words we will not use to scare bees

- “Zero-day” without a box and a VLAN
- “Game over” because a blog said 10.0
- “We are fine” because the score is 3.1 and the box is the till

Fill one card per hole that Wazuh or a vendor yells about. Stick it next to `software.md`.
