# ECD Evidence Rubric — Reachy Mini Cybersecurity Modules

> Maps student claims to acceptable evidence and the exercise template that produces it. Use as your grading instrument.

---

## How to use

1. For each module, pick **one or two** claims this rubric supports.
2. List the artifacts you'll collect.
3. Score each artifact on a 0–3 scale per the criteria below.
4. The grade is *not* "did the exploit work" — it's "does the evidence support the claim."

---

## Claims and evidence

### Claim 1 — Surface awareness
> Student can describe the attack surface of a small networked AI device.

**Evidence:** A labeled diagram naming at least four layers, with one realistic vector per layer.

**Where it shows up:** T1 reflection · T6 threat model · T7 defense brief

**Scoring:**
- 0 — fewer than 3 layers, no vectors
- 1 — 3 layers, vectors imprecise
- 2 — 4+ layers, plausible vectors per layer
- 3 — 5 layers, vectors named with mitigation pairing

---

### Claim 2 — Network reading
> Student can read network traffic and identify a control protocol.

**Evidence:** Annotated packet capture showing the relevant frames and what they encode.

**Where it shows up:** T1 capture · T3 recon log

**Scoring:**
- 0 — capture present but unannotated
- 1 — frames identified, fields not interpreted
- 2 — fields interpreted, control semantics named
- 3 — adds a counterfactual ("if this field were absent, …")

---

### Claim 3 — Failure analysis
> Student can articulate why a given control failed.

**Evidence:** Written explanation that names the layer, the assumption that broke, and a mitigation.

**Where it shows up:** T1 reflection · T2 reflection · T3 commit message · T5 brief

**Scoring:**
- 0 — outcome described, no causal attribution
- 1 — layer named, assumption vague
- 2 — layer + assumption + plausible mitigation
- 3 — adds the cost of the mitigation

---

### Claim 4 — Characterization (not just demonstration)
> Student can characterize, not just demonstrate, an AI-pipeline attack.

**Evidence:** Small table of conditions under which the attack succeeded and failed, plus a paragraph on transferability.

**Where it shows up:** T2 in-class taxonomy · T4 detection-rate table

**Scoring:**
- 0 — single successful demo, no conditions
- 1 — conditions tabulated, no transferability discussion
- 2 — conditions + transferability discussion
- 3 — adds a hypothesis about *why* transferability behaves the way it did

---

### Claim 5 — Layered defense design
> Student can design and defend a layered defense.

**Evidence:** Defense brief naming controls by layer, residual risk, and at least one accepted trade-off.

**Where it shows up:** T7 defense brief · partial credit in T6 after-action report

**Scoring:**
- 0 — controls listed without layer attribution
- 1 — controls per layer, no residual risk
- 2 — controls + residual risk + one trade-off
- 3 — controls + residual risk + multiple trade-offs with reasoning

---

### Claim 6 — Ethical action under uncertainty
> Student can act ethically under uncertainty.

**Evidence:** Reflection naming a moment they chose not to do something, and why; signed responsible-disclosure form on file.

**Where it shows up:** Any reflection in any module.

**Scoring:**
- 0 — no signed form OR no reflection on choice
- 1 — signed form, generic reflection
- 2 — signed form + named a specific moment of restraint
- 3 — signed form + restraint moment + reasoning that generalizes

---

### Claim 7 — Reproducibility
> Student can produce work a peer can replicate.

**Evidence:** Repository (or fork) with a README that lets the next student rerun the exercise from scratch.

**Where it shows up:** T3 · T5 · T6 · T7

**Scoring:**
- 0 — code present, no README
- 1 — README present, missing dependencies or setup
- 2 — README is sufficient for a peer to rerun
- 3 — README is sufficient for a peer one cohort behind to rerun

---

## Aggregate

For a single module, expect to grade against **2–3 claims**, not all seven. A semester-long course should cover all seven across modules.

A student's final grade for the module is the average of their per-claim scores, weighted equally. Do not curve.

---

## Why this rubric

Most cybersecurity courses grade on whether the exploit worked. That conflates skill with luck and rewards spectacle over understanding. ECD-style grading rewards the student who failed to exploit a system but produced a clear writeup of why the system was actually well-defended — which is closer to the work practitioners actually do.
