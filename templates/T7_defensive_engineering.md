# T7 — Defensive Engineering (harden a deployment, then defend it)

**Tier:** Advanced · **Duration:** 2 week project · **Group size:** 3–4 students per team

---

## Learning outcome

> By the end of this module, students can design, implement, and document a defense-in-depth posture for a small embodied AI deployment, and can defend their decisions in a peer review.

---

## Prerequisites

- Each team is assigned a robot and a deployment scenario:
  - Classroom assistant
  - Lobby greeter
  - Lab demo unit
  - Children's hospital companion (advanced — extra ethics scrutiny)
- Each team must implement **at least four defensive controls**, each from a different layer of the attack-surface map
- A peer team will run a constrained attack against their hardened system at the end of week 2

---

## Run sheet (two weeks)

### Week 1 — Threat model + implementation

**Day 1 (in class, 90 min)** — Threat model session
- Identify the deployment's adversaries (who, with what motivation, with what capability)
- Identify the assets (data, behavior, reputation)
- Map adversaries × assets → priority controls

**Day 2–5 (out of class, ~8 hr per team)** — Implementation
- Pick ≥4 controls, each from a different attack-surface layer
- Implement them. Configuration goes in the team's repo.
- Document each control: what it protects, against what, with what residual risk

### Week 2 — Defense brief, attack window, peer review

**Day 1** — Submit defense brief (see template below)
**Day 2** — Other teams read briefs, prepare attack plan
**Day 3** — Peer attack window (2 hr, attacks must respect responsible-disclosure agreement)
**Day 4** — Cool down
**Day 5** — Peer-reviewed writeup (each team grades the other's brief on a published rubric)

---

## Defense brief template (give to students)

```
DEFENSE BRIEF — TEAM <name>

DEPLOYMENT SCENARIO
  <one paragraph: where, who uses it, what's at stake>

THREAT MODEL SUMMARY
  Adversaries:
    - <who>, capability: <what>, motivation: <why>
  Assets:
    - <what>, value: <how lost looks>

CONTROLS IMPLEMENTED
  Layer: <network|app|AI/ML|supply-chain|physical|privacy>
  Control: <what>
  Protects against: <which adversary, which asset>
  Residual risk: <what we accept>
  Trade-off accepted: <latency|UX|cost|complexity>
  How a peer can verify: <command, file, observation>
  [repeat for ≥4 controls]

WHAT WE EXPLICITLY CHOSE NOT TO DEFEND
  <one paragraph and reasoning>

OPEN QUESTIONS
  <what the team is genuinely unsure about>
```

A 4-control brief should be ~3–4 pages. Anything longer is probably padding.

---

## Suggested controls by layer

(Don't hand this to students — let them propose. Use as TA reference.)

- **Network:** mTLS for SDK channel · explicit allowlist of client IPs · WPA-Enterprise instead of PSK · network segmentation
- **Application:** signed prompts/messages · rate-limiting per token · token rotation · audit log shipped off-device
- **AI/ML:** input-output policy filter · model output classifier · refusal-rate monitoring
- **Supply chain:** signed dependency manifest · private package index · pinned model weights with hashes
- **Physical:** hardware camera shutter with status LED · tamper-evident enclosure · port covers
- **Privacy:** data-retention defaults · explicit consent for camera/mic activation · audit access to logs

---

## Evidence collected (5 artifacts)

1. Defense brief (above)
2. Configuration diff against baseline (in repo)
3. Audit log captured during the peer attack window
4. Peer-review feedback received
5. Team's response to peer feedback (one page)

---

## Peer-review rubric (publish before week 2)

For each control in the reviewed team's brief, score 0–3:

- **Specificity** — is the control concrete enough to verify? (0 = vague; 3 = "I can run this command and see it")
- **Layering** — does it actually live at a different layer than the others, or is it duplicate-by-different-name?
- **Residual risk honesty** — did they admit what they didn't fix?
- **Trade-off honesty** — did they name what the control cost?

Plus one rubric item for the brief overall:

- **Falsifiability** — could this brief be wrong? Does it make claims a peer attack could disprove?

---

## Common pitfalls

- **Four controls all in the same layer.** Reject and ask for revision before the attack window.
- **No residual risk.** Push back hard — "what would still break this?" If they can't answer, the brief isn't done.
- **Peer review devolves into "I would have done it differently."** Anchor every comment to the rubric.

---

## Debrief prompts (after week 2)

**Tier 1**
- "Which of your controls actually got tested in the attack window? Which were never probed?"
- "What surprised you in the audit log?"

**Tier 2**
- "If you had one more week, which control would you add and why?"
- "Which control will you remove if your boss asks you to cut latency in half?"

**Tier 3**
- "Is the deployment safe enough to ship? Whose decision is that, really?"
- "What did this exercise teach you about the cost of security beyond the technical work?"

---

## Why this is the strongest portfolio module

Encourage students to publish their defense brief (suitably redacted) on a personal site. It makes a strong job-search piece because:
- It demonstrates layered thinking, not just exploit-finding
- It shows ability to write to a non-engineer audience (the curator persona)
- It includes peer feedback they responded to (which is rare in undergrad work)

---

## Connection to other modules

- Closes the loop opened by **T1** (the channel they attacked there is the channel they defend here)
- Pairs with **T6** as the second half of an advanced sequence: red/blue then defense engineering
- Anchors the ECD evidence rubric for Claims 1, 5, 6, and 7 simultaneously
