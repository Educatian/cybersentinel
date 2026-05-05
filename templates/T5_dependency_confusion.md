# T5 — Dependency Confusion (where did pip install just go?)

**Tier:** Intermediate · **Slot:** 75 min · **Group size:** 2 students per laptop

---

## Learning outcome

> By the end of this module, students can explain how the Python packaging ecosystem resolves package names, identify three concrete misconfigurations that lead to malicious package installation, and configure pip to refuse them.

---

## Prerequisites

- A local PyPI mirror inside the lab network with one "internal" package, e.g., `reachy-mini-utils v1.0.0`
- A benign-but-clearly-marked package with the **same name** published to public PyPI under a sandbox account. The package's only behavior is:
  ```python
  print("⚠️  You installed the wrong reachy-mini-utils. See course syllabus §T5.")
  ```
- A `requirements.txt` handed to students that **omits** the internal index URL
- IRB protocol explicitly names the sandbox PyPI account

---

## Run sheet

| # | Verb | Step | Min |
|---|------|------|-----|
| 1 | Install | `pip install -r requirements.txt` in a fresh virtualenv with internet enabled. Most groups see the public package's print statement. | 10 |
| 2 | Investigate | Why did pip pick the public package? Walk through resolution order, version precedence, `--index-url` vs `--extra-index-url`. | 20 |
| 3 | Fix | Rewrite the install pipeline using a private index, hash-pinning, and a lock file. Each fix is a separate commit. | 25 |
| 4 | Generalize | Discuss the same class of failure in npm, Maven, Go modules. Connect to public dependency-confusion incidents. | 20 |

**Total:** 75 min

---

## Evidence collected (3 artifacts)

1. Before/after install logs (showing pip's resolution path)
2. Corrected configuration files (committed)
3. One-page brief: "How the same vulnerability would manifest in [npm | Maven | go modules — student picks one]"

---

## Authoring notes

- **The sandbox package must be harmless.** Print only. No telemetry. No file writes. No network calls. Document this in your IRB protocol.
- **Clearly attribute** the sandbox package: include the course name and a contact email in the package description on PyPI.
- **Yank the sandbox package** from PyPI at the end of each semester so it doesn't become an attractive nuisance.
- **Don't reuse package names** between semesters — students from a prior semester might still have it cached.

---

## Common pitfalls

- **Students think the public package is "the bug" and the local one is "fine."** The bug is the resolution rule, not either package.
- **Lock-file discussion drifts.** Keep step 3 focused on three concrete pip flags: `--index-url`, `--require-hashes`, and a `pip-compile`-generated lock.
- **Generalization step gets hand-wavy.** Provide a one-paragraph reading per ecosystem (npm, Maven, go) and have students cite it in their brief.

---

## Reference incidents to discuss in step 4

- Birsan, A. (2021) — original dependency confusion writeup, attacked Apple/Microsoft/PayPal etc.
- Various npm typosquatting incidents (let students search and pick one)
- Real-world model-poisoning analogue on Hugging Face (research literature, ongoing)

Don't lecture; ask each group to bring one incident to the discussion.

---

## Debrief prompts

**Tier 1**
- "Walk me through pip's decision in step 1. Where did it look first, second, third?"
- "Which of your three commits in step 3 actually closed the vulnerability? Which were defense-in-depth?"

**Tier 2**
- "If you were a vendor publishing an internal package, what's the smallest discipline that would prevent this?"
- "Hash-pinning has costs. Name two."
- "Why does this vulnerability persist across ecosystems despite being well-documented since 2021?"

**Tier 3**
- "Have you ever installed a package without checking what it pulled in transitively? What would change if you did?"
- "If you maintain a small open-source library, what's *your* obligation here?"

---

## Connection to other modules

- Pairs with **T3** as a "supply chain hygiene" week
- Feeds into **T7** — defense brief should name a supply-chain control (lock file, signed manifest, private index)
- Sets up a research handle: longitudinal "do students change their pip habits 6 months later" survey
