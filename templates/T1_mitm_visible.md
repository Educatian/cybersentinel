# T1 — Visible MITM ("the robot looks the wrong way")

**Tier:** Beginner · **Slot:** 60 min · **Group size:** 3 students per robot

---

## Learning outcome

> By the end of this module, students can explain, in their own words, why plaintext control protocols are unsafe even on a "trusted" local network, and can name two mitigations.

---

## Prerequisites

- Wireshark installed on every laptop
- `mitmproxy` installed on the TA "attacker" laptop
- A working baseline control script that sends `look_at(x, y)` once per second based on cursor position
- Verified: the script runs against the current SDK version pinned in the course README

---

## Run sheet

| # | Verb | Step | Min |
|---|------|------|-----|
| 1 | Run | Each group runs the baseline control script. Robot tracks cursor. Capture 1 min of traffic with Wireshark. | 10 |
| 2 | Inspect | Open the capture in Wireshark. Identify the control frames. List which fields are readable in plaintext. | 15 |
| 3 | Intercept | TA enables mitmproxy with a script that flips x and y signs. Groups re-run the control script — robot now mirrors. | 15 |
| 4 | Reflect | Whole-class discussion: propose mitigations. Drive toward TLS, MAC, and "trusted local network" as a fallacy. | 15 |
| 5 | Write | Start one paragraph in class: what they observed, what changed, what they'd change as Pollen Robotics. Finish at home. | 5 |

**Total:** 60 min

---

## Evidence collected (3 artifacts)

1. Wireshark `.pcapng` from step 1
2. Screen recording of the mirrored behavior from step 3
3. One-paragraph reflection (graded against ECD Claim 2 + Claim 3)

---

## Common pitfalls

- **Students attribute the bug to "the script" rather than the channel.** Force them to point at the captured frame in Wireshark.
- **Some groups want to run more sophisticated attacks.** Save those for T6 — the goal here is one clean observation.
- **Wireshark filters confuse beginners.** Pre-load a filter profile that highlights the relevant frames.

---

## Authoring notes for the TA

The "wow" moment is step 3. Manage room expectations during step 2 so the demo lands:
- Don't let students see the mitmproxy script before step 3
- Position the robot so the whole room can see the head movement
- Have one group volunteer to run their script "live" in front of everyone

---

## Debrief prompts (use template, customize these)

**Tier 1**
- "When you saw the head turn the wrong way, what was the first thing you thought caused it?"
- "Point at the field in your Wireshark capture that the attacker actually changed."
- "What did the network do that allowed this attack to work?"

**Tier 2**
- "Whose responsibility is it to encrypt traffic on a local network — the device vendor, the network operator, or the application developer?"
- "What would TLS cost the user, in latency or setup?"
- "Why might a vendor ship plaintext on local network even knowing this risk exists?"

**Tier 3**
- "Where else in your house or office is there a 'trusted local network' assumption?"
- "If you noticed this in a product you owned tomorrow, what would you do?"

---

## Variant for online / hybrid

If you can't be in person:
- TA streams the robot's head on camera
- Students share screen for the Wireshark and script work
- The "wow" of seeing the head move loses some force on a webcam — compensate by showing two angles of the robot

---

## Connection to other modules

- Pairs naturally with **T7** (defensive engineering) one or two weeks later — students see the problem here, defend against it there.
- Don't run **T6** in the same week as T1 — students need at least two intermediate exercises before a capstone is meaningful.
