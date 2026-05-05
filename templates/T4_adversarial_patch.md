# T4 — Adversarial Vision Patch (fooling the camera with paper)

**Tier:** Intermediate · **Slot:** 90 min · **Group size:** 3–4 students per robot

---

## Learning outcome

> By the end of this module, students can describe what an adversarial example is, generate or download a working patch, and demonstrate that the robot's vision-driven behavior changes in a controlled way when the patch is present.

---

## Prerequisites

- Configure the robot to perform a simple vision-triggered behavior (e.g., wave when it detects a person in frame)
- Provide students with **2–3 pre-generated adversarial patches** printed on letter-size paper. Authoring novel patches in 90 minutes is unrealistic; the pedagogical work is in *using and characterizing* them.
- Lighting in the room is consistent (close blinds; consistent overhead light)
- A clipboard for each group to record detection counts

---

## Run sheet

| # | Verb | Step | Min |
|---|------|------|-----|
| 1 | Baseline | Confirm the robot waves at people. Record baseline detection rate over 20 trials. | 15 |
| 2 | Hold | Each student stands in front of the robot holding each patch. Record new detection rate over 20 trials per patch. | 30 |
| 3 | Discuss | Why does a patch trained against model A sometimes work against model B? When does it not? | 15 |
| 4 | Threat-model | Sketch a threat model: where in a real-world system is this attack realistic, where is it not, and what mitigation would you recommend? | 20 |
| 5 | Write | Detection-rate table + one paragraph on transferability + one paragraph on threat model. | 10 |

**Total:** 90 min

---

## Evidence collected (3 artifacts)

1. Detection-rate table (baseline vs. patch A vs. patch B vs. patch C)
2. Photos of the patch-in-use (no faces, hands and patches only)
3. Threat-model sketch + paragraphs

---

## Conservative framing (read aloud at start)

> *"Adversarial robustness is an active research area. Today's patches may or may not work — model and lighting vary. Your job is to **characterize what happens when**, not to demonstrate that the patch always works. A 'failed' patch is still a successful exercise if you produce a clean detection-rate table."*

This framing matters. It also keeps you out of overclaiming territory if a reviewer ever sees the writeup.

---

## Common pitfalls

- **Inconsistent posture.** Students hold the patch at different distances and angles, which adds noise. Mark a tape line on the floor for "patch position."
- **Race to "make it work."** A group whose patch never works is a useful data point — protect them from feeling like they failed.
- **Camera autofocus.** Some patches lose effectiveness when out of focus. Note this in the table.

---

## Detection-rate table format

| Condition | Trials | Detections | Rate |
|-----------|--------|------------|------|
| Baseline (no patch) | 20 | _ | _ |
| Patch A | 20 | _ | _ |
| Patch B | 20 | _ | _ |
| Patch C | 20 | _ | _ |

Bonus row: "Baseline at end of session" — re-run baseline at the end to confirm the model didn't drift during the exercise.

---

## Debrief prompts

**Tier 1**
- "Which patch worked best? Which worked worst? What might explain the difference?"
- "What changed between trial 1 and trial 20 for the same patch?"

**Tier 2**
- "If you were Pollen Robotics, would you defend against adversarial patches? At what cost?"
- "What detection-rate threshold would make you say 'this patch is a real risk'?"
- "Whose problem is this — the model trainer, the device integrator, or the deployer?"

**Tier 3**
- "Where in the real world is the attacker likely to have time to put paper in front of a camera? Where do they not?"
- "What does 'adversarial robustness' translate to in non-vision systems? In your own field?"

---

## Optional advanced extension

For students who finish the table early:
- Read Goodfellow et al. (2015) *Explaining and harnessing adversarial examples*
- Sketch (no code) how they would generate their own patch against this specific model
- Discuss in the next class

---

## Connection to other modules

- Strong pairing with **T2** in the same week — voice and vision are two pipeline-attack angles on the same device
- Feeds into **T7** — defense brief should name a vision-pipeline control
