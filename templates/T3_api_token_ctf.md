# T3 — API Token CTF (find the leak, exploit it, fix it)

**Tier:** Intermediate · **Slot:** 90 min · **Group size:** 2–3 students per robot

---

## Learning outcome

> By the end of this module, students can identify three common patterns of credential exposure in a small Python codebase, demonstrate exploitation in a controlled setting, and propose a remediation for each.

---

## Prerequisites

- A deliberately vulnerable companion repo authored by you, planted with three credential issues:
  1. **Hardcoded token** in a committed `.py` file
  2. **Token logged** in a debug `print()` that ships to a logfile
  3. **Token derivable** from a predictable seed (e.g., `secrets.token_hex(seed=robot_serial)`)
- The repo URL is the *only* hint students get
- Lab WiFi password (everyone already has it)
- A "harmless command" budget — the only thing students can do with a stolen token is wiggle the robot's head

---

## Run sheet

| # | Verb | Step | Min |
|---|------|------|-----|
| 1 | Recon | Enumerate the lab network with nmap and mDNS. Find the robot. Find the companion app. | 20 |
| 2 | Read | Clone the repo and read it. **Forbid running it yet.** Find leaks by inspection. | 20 |
| 3 | Exploit | Each found credential lets them issue one head-wiggle command via the SDK. | 20 |
| 4 | Fix | Open a pull request that fixes one of the three issues, with a one-paragraph commit message. | 20 |
| 5 | Debrief | Show the three issue patterns side by side. Connect each to a real-world breach. | 10 |

**Total:** 90 min

---

## Evidence collected (3 artifacts)

1. Nmap output + the three credential discoveries with file:line citations
2. Screen recording of the head-wiggle exploit (proof of access)
3. The remediation pull request

---

## Authoring notes (for the TA building the companion repo)

Make the planted bugs realistic. Students see through "obviously fake" bugs and the reflective discussion suffers.

**Bug 1 — Hardcoded token** — borrow shape from real OWASP cheat-sheet examples:
```python
# config.py
ROBOT_API_TOKEN = "tok_live_8f3a9c2e7b1d4a6f"  # REMOVE BEFORE PUSHING
```
Yes, leave the comment in. Students should see the comment and still miss it the first read.

**Bug 2 — Logged token** — embed in a debug helper:
```python
def debug_request(url, headers):
    logger.debug(f"GET {url} headers={headers}")  # headers includes Authorization
```
Set `LOG_LEVEL=DEBUG` in the default `.env.example`.

**Bug 3 — Derivable token** — common interview-question pattern:
```python
def make_session_token(robot_id):
    random.seed(int(robot_id))  # deterministic by design
    return ''.join(random.choices(string.ascii_letters, k=24))
```

---

## Common pitfalls

- **Students brute-force run the code instead of reading it.** Step 2 is a "no execution" zone for a reason — credential discovery by inspection is the skill.
- **Groups race to find all three.** Encourage finding any one, then helping a slower group. The PR step is a better differentiator than speed.
- **PRs are sloppy.** Give 5 of the 20 step-4 minutes to "what makes a good commit message," and they'll produce work you can actually grade.

---

## Debrief prompts

**Tier 1**
- "Which bug did your group find first? Which last? Why?"
- "What pattern in the code made the third one the hardest?"

**Tier 2**
- "Which of these three bugs would have made it past the *current* code review process at your last internship/job?"
- "What single tooling change would have caught all three?" (Hint to look for: pre-commit hooks, secret scanners, hash-pinning.)

**Tier 3**
- "If you found a hardcoded token in a public repo tomorrow, what would you do? Who do you contact?"
- "What's the difference between responsibly reporting it and getting yourself in trouble?"

---

## Connection to other modules

- Builds on **T1** (network awareness) and prepares for **T6** (capstone chains a credential leak into a multi-step attack)
- Pairs naturally with **T5** in the same syllabus week — credentials and dependencies are both supply-chain hygiene
