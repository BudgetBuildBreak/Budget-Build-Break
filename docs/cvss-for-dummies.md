# CVSS Scorecard for Beginners

## What is CVSS?

**CVSS (Common Vulnerability Scoring System)** is a way to describe **how serious a software vulnerability could be**.

Think of it like a severity rating.

The score goes from **0.0 to 10.0**:

|        Score | Severity | What it means                                  |
| -----------: | -------- | ---------------------------------------------- |
|      **0.0** | None     | No security impact                             |
|  **0.1–3.9** | Low      | Minor risk                                     |
|  **4.0–6.9** | Medium   | Significant enough to investigate              |
|  **7.0–8.9** | High     | Should be addressed soon                       |
| **9.0–10.0** | Critical | Serious vulnerability; investigate immediately |

### Important:

**CVSS tells you how dangerous a vulnerability can be. It does not tell you how dangerous it is to your specific network.**

A vulnerability with a CVSS score of 10.0 means very little if you don't use the affected software.

A vulnerability with a CVSS score of 4.5 could be extremely important if it affects a critical system on your network.

**CVSS is the starting point. Your environment determines the actual risk.**

---

# How is the CVSS score calculated?

CVSS looks at several questions about the vulnerability.

You do not need to memorize the abbreviations. Just understand what each question is asking.

## 1. How can someone attack it?

### Attack Vector — AV

**Where does the attacker need to be?**

* **Network** — They can attack it remotely over the network or internet.
* **Adjacent** — They must be on the same nearby network, such as the same Wi-Fi.
* **Local** — They already need access to the computer.
* **Physical** — They need physical access to the device.

**Easy way to remember it:**

> The farther away an attacker can be, the more concerning the vulnerability generally is.

---

## 2. How difficult is the attack?

### Attack Complexity — AC

**Does the attack work easily, or does it require special conditions?**

* **Low** — The attacker can perform the attack with little difficulty.
* **High** — The attacker needs specific conditions, timing, or additional steps.

**Example:**

If clicking one button triggers the vulnerability, that is relatively simple.

If the attacker needs the system to be in a very specific state at exactly the right moment, that is more complex.

---

## 3. Does the attacker need an account?

### Privileges Required — PR

**Does the attacker already need permission to use the system?**

* **None** — No account or existing access is required.
* **Low** — A basic user account is required.
* **High** — Administrator or another highly privileged account is required.

**Think of it as keys:**

* No key = anyone can try.
* User key = they need an account.
* Administrator key = they need significant access already.

---

## 4. Does someone have to do something?

### User Interaction — UI

**Does another person have to take an action for the attack to work?**

* **None** — The attacker can perform the attack without another person's help.
* **Required** — Someone must click, open, run, approve, or otherwise interact with something.

For example:

> An attacker sends a malicious file, but the employee has to open it.

That requires **User Interaction**.

---

# 5. Does the vulnerability escape the system?

### Scope — S

**If the attacker exploits this vulnerability, does the damage stay inside the affected system, or can it affect something else?**

* **Unchanged** — The attacker stays within the security authority of the vulnerable system.
* **Changed** — Exploiting the vulnerability allows the attacker to affect another security authority or system.

### Simple example

Imagine a web application running on a server.

If exploiting the vulnerability only gives the attacker control of that application, the scope is **Unchanged**.

If exploiting the application allows the attacker to gain control of another system or security boundary, the scope is **Changed**.

**Think:**

> Does the attack stay inside the fence, or does it let the attacker jump the fence?

---

# What can the attacker actually do?

The next three questions describe the **impact** of the vulnerability.

## 6. Can they read information?

### Confidentiality — C

**Can the attacker access information they should not be able to see?**

* **None** — They cannot access protected information.
* **Low** — They can access some information.
* **High** — They can access significant or highly sensitive information.

Think:

> **Can they read it?**

---

## 7. Can they change information?

### Integrity — I

**Can the attacker modify information or systems?**

* **None** — They cannot change anything.
* **Low** — They can make limited changes.
* **High** — They can make significant changes.

Think:

> **Can they change it?**

---

## 8. Can they stop the system from working?

### Availability — A

**Can the attacker make the system unavailable or unusable?**

* **None** — The system continues operating normally.
* **Low** — Performance or availability is partially affected.
* **High** — The system can be seriously disrupted or taken offline.

Think:

> **Can they break it or make it unavailable?**

---

# The easiest way to remember CVSS

When looking at a vulnerability, ask:

### **HOW DO THEY GET IN?**

**AV** — Where do they attack from?

**AC** — How difficult is the attack?

**PR** — Do they need an account?

**UI** — Does someone have to help them?

**S** — Can the attack cross a security boundary?

### **WHAT CAN THEY DO?**

**C** — Can they read information?

**I** — Can they change information?

**A** — Can they disrupt the system?

That's the basic idea behind the CVSS score.

---

# A simple example

Imagine a vulnerable web server.

An attacker can exploit it:

* remotely over the internet,
* without an account,
* without anyone clicking anything,
* using a simple attack,
* and the vulnerability allows them to read, modify, and disrupt the system.

That is a **very serious vulnerability**.

Now imagine another vulnerability:

* requires physical access,
* requires an existing administrator account,
* requires several complicated steps,
* and only allows the attacker to read a small amount of information.

That vulnerability may receive a **much lower CVSS score**.

---

# But CVSS is NOT the final answer

This is the part that matters most when you're actually managing a network.

**CVSS describes the vulnerability. Your environment determines your risk.**

Before panicking over a CVSS score, ask:

### 1. Do we actually use the affected software?

If not, the vulnerability may not apply to us.

### 2. Where does the affected system live?

Is it:

* Internet-facing?
* On an internal network?
* On a workstation?
* On a server?
* On an isolated VLAN?
* On a critical business system?

### 3. Who can reach it?

A vulnerability that requires network access is much more concerning when the vulnerable system is exposed to the internet than when it is isolated behind several security controls.

### 4. What would happen if it were compromised?

Could an attacker:

* steal sensitive information?
* modify important data?
* take down a critical service?
* move to another system?
* gain administrator access?

### 5. Can we fix it?

Possible responses include:

* **Patch** the software.
* **Upgrade** to a fixed version.
* **Disable** the vulnerable feature.
* **Restrict access** with firewall rules or network segmentation.
* **Isolate** the system.
* **Apply another compensating control** when a patch is not available.

---

# Beginner CVSS Scorecard

Use one card for each vulnerability.

## Vulnerability

**Name:** __________________________________________

**CVE:** ____________________________________________

**Affected system:** _________________________________

**VLAN / Network:** __________________________________

**CVSS Score:** __________ / 10

**Severity:**  ☐ Low  ☐ Medium  ☐ High  ☐ Critical

---

## How is it attacked?

**Attack Vector — Where does the attacker need to be?**

☐ Network / Internet
☐ Same local network
☐ Local computer access
☐ Physical access

**Attack Complexity**

☐ Low — relatively easy
☐ High — requires special conditions

**Privileges Required**

☐ None
☐ Low / normal user
☐ High / administrator

**User Interaction**

☐ None
☐ Required — someone must take an action

**Scope**

☐ Unchanged — stays within the affected system
☐ Changed — can cross a security boundary

---

## What can the attacker do?

**Confidentiality — Can they read information?**

☐ None
☐ Low
☐ High

**Integrity — Can they change information?**

☐ None
☐ Low
☐ High

**Availability — Can they disrupt the system?**

☐ None
☐ Low
☐ High

---

# Now look at OUR network

### Does the affected software actually exist here?

☐ No — vulnerability does not apply to our environment.

☐ Yes — continue the assessment.

**Where is it?**

VLAN: ______________________

System: ____________________

---

### Can an attacker reach it?

☐ Internet
☐ Internal network
☐ Restricted network
☐ Isolated network
☐ Physical access only

---

### How important is this system?

☐ Low importance
☐ Normal business system
☐ Important business system
☐ Critical system

---

### What is our response?

☐ **Patch** — install the available fix.

☐ **Upgrade** — move to a supported version.

☐ **Restrict** — limit who or what can reach it.

☐ **Isolate** — separate the system from other systems.

☐ **Compensate** — use another security control because we cannot patch it yet.

☐ **Accept** — document why the remaining risk is acceptable.

☐ **Not applicable** — affected software/system does not exist here.

**Reason / Notes:**

---

---

---

---

# Monitoring

**Is the system enrolled in our monitoring tools?**

☐ Yes
☐ No
☐ Not applicable

**Are we watching for signs of exploitation?**

☐ Yes
☐ No

---

# Three rules to remember

### 1. A high CVSS score does not automatically mean YOUR network is in danger.

If you don't use the affected software, the vulnerability may not apply to you.

### 2. A lower CVSS score does not automatically mean the vulnerability is safe to ignore.

A moderate vulnerability on a critical system may deserve more attention than a critical vulnerability on an isolated, unused system.

### 3. CVSS is the starting point — not the decision.

**CVSS tells you how serious the vulnerability can be.**

**Your network tells you how serious it is for you.**

---

# The One-Sentence Version

> **CVSS tells us how bad a vulnerability could be. Our job is to determine whether that vulnerability exists in our environment, what it can reach, what it can affect, and what we should do about it.**

That's the entire concept.

Don't let a scary number make the decision for you.

