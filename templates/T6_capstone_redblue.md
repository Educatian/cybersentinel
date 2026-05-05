# T6 — Capstone: Full-Chain Red vs Blue

**Tier:** Advanced · **Duration:** 1 week project · **Group size:** Two teams of 3–4 students per robot

---

## Learning outcome

> By the end of this module, students can chain three or more techniques into an end-to-end attack against a controlled target, and a parallel team can detect and contain the attack in real time. Both teams produce a written reflection that names what they did and what they wish they had done.

---

## Prerequisites

- Students have completed **at least three** of T1–T5 already
- Two teams per robot
- A neutral observer (the TA) who logs every action with a timestamp
- A scenario brief (see below)

---

## Scenario brief (customize)

> *"The robot is being prepared for deployment as a museum greeter at the [University] Discovery Center, opening day next month. The curator wants you to find every realistic compromise path before then. Red team will model an opportunistic attacker with local-network access (e.g., a curious visitor with a laptop). Blue team will model the museum's IT operations group with three days to harden the deployment. After day 5 you will face each other in a controlled engagement. After day 7 you will jointly author the after-action report the curator will read."*

---

## Run sheet (one week)

### Day 1 — Threat model (90 min in class)
- Both teams independently produce a threat model document
- Compare: surface the gaps between the two models
- This is graded — see ECD Claim 1

### Day 2–4 — Build (out of class, ~6 hr per team)
- **Red team:** Build an exploit chain that uses *at least three* layers of the attack-surface map. Document each step.
- **Blue team:** Build detections, response runbook, and rollback plan. Document each control.
- Both teams check in with the TA at end of day 3

### Day 5 — Live exercise (2 hr controlled engagement)
- Engagement window opens at a fixed time
- Red team executes their chain
- Blue team detects, contains, recovers
- Observer (TA) logs every action with a timestamp on a shared timeline
- Engagement ends regardless of "success" at the 2-hour mark

### Day 6 — Cool down (no class)

### Day 7 — Joint writeup (90 min in class + finish at home)
- Both teams co-author a single after-action report
- The grade is on the report's honesty, not on who "won"

---

## Evidence collected (5 artifacts)

1. Both threat-model documents (Day 1)
2. Red team exploit chain code + documentation
3. Blue team detection rules + runbook
4. Observer's timestamped action log
5. Joint after-action report (Day 7)

---

## After-action report structure (give to students)

1. **What happened** — a single shared timeline both teams agree on
2. **What worked for the attacker** — three to five specific moments
3. **What worked for the defender** — three to five specific moments
4. **What we both missed** — gaps neither side noticed in advance
5. **What we'd do differently** — one paragraph each, signed
6. **Recommendations to the curator** — a prioritized list ready to hand off

---

## Why a *joint* report

Joint authorship forces both teams to build a shared mental model. Students who only see their own side leave with a shallow understanding of the other. Grading rewards teams whose joint report includes *at least one* finding that neither side would have written alone.

---

## Common pitfalls

- **One team dominates the writeup.** Set a hard rule: each numbered section must have at least one paragraph from each team, attributed.
- **Red team romanticizes the win.** Push them to describe what almost stopped them.
- **Blue team is defensive about misses.** Frame this as the most valuable kind of evidence.
- **Engagement window runs over.** Hard-stop at 2 hours. The cool-down day matters.

---

## Observer (TA) action log format

| Time | Team | Action | What was visible to the other team? |
|------|------|--------|-------------------------------------|
| 14:02 | Red | nmap scan | nothing |
| 14:05 | Blue | tcpdump started | n/a |
| 14:11 | Red | mDNS query for `_reachy._tcp` | logged in tcpdump |
| ...   |     |                                |                              |

This log is the most valuable artifact for grading and for next semester's TA.

---

## Debrief prompts

**Tier 1**
- "Walk me through the engagement timeline. Where did the two narratives diverge?"
- "What was the first action either team took that the other side noticed?"

**Tier 2**
- "If you were the curator, what control would you fund first based on this exercise?"
- "What's a control that *sounds* good but the exercise showed wouldn't have helped?"

**Tier 3**
- "What did you learn about the other side's job?"
- "If you went into industry tomorrow as red or blue, what would you carry with you from this week?"

---

## Connection to other modules

- Capstone for the entire course; expects T1, T3, T5 minimum already done
- Naturally precedes **T7** (defensive engineering) — same students, deeper defense
- Produces the strongest portfolio piece (joint after-action report) of any module
