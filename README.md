# CyberSentinel

> **Reachy Mini WiFi as a cybersecurity teaching surface.**
> A practical onboarding guide for graduate-student instructional designers who want to build hands-on cybersecurity exercises around a small, visible, networked robot — without needing a formal infosec background.

**Live guide:** [educatian.github.io/cybersentinel](https://educatian.github.io/cybersentinel)

---

## What's here

A self-contained HTML guidebook (`index.html`) plus 13 editable Markdown templates (`templates/`) that grad-student TAs can fork into their own course repo to author defensible, ethics-reviewed cybersecurity learning modules.

| Path | What it is |
|------|------------|
| `index.html` | Single-file guidebook — sticky TOC, attack-surface map, 7 exercise cards, ECD rubric, IRB gate, 90-min author worksheet |
| `templates/module_builder_worksheet.md` | The 90-minute author worksheet |
| `templates/debrief_script.md` | Three-tier debrief prompts (technical / design / transfer) |
| `templates/ecd_evidence_rubric.md` | Claim → evidence → task mapping for grading |
| `templates/lab_safety_checklist.md` | Hardware / software / network / reset checklists |
| `templates/irb_gate_checklist.md` | IRB & informed-consent gate, with draft consent paragraph |
| `templates/T1_mitm_visible.md` | Visible MITM exercise scaffold (Beginner, 60 min) |
| `templates/T2_voice_prompt_injection.md` | Voice prompt injection exercise (Beginner, 60 min) |
| `templates/T3_api_token_ctf.md` | API token CTF (Intermediate, 90 min) |
| `templates/T4_adversarial_patch.md` | Adversarial vision patch (Intermediate, 90 min) |
| `templates/T5_dependency_confusion.md` | Dependency confusion (Intermediate, 75 min) |
| `templates/T6_capstone_redblue.md` | Red vs blue capstone (Advanced, 1 week) |
| `templates/T7_defensive_engineering.md` | Defensive engineering capstone (Advanced, 2 weeks) |

The guide also carries a **§13 Tentative ideas — beyond cybersecurity** section sketching seven non-infosec directions where the same Reachy Mini hardware and the ECD/IRB scaffolding here would transfer (embodied tutoring, counseling skill simulation, pre-service teacher × child agent, joint attention, multimodal VLM, robot-mediated LA feedback, Quest 3 head-tracking telepresence). Treat them as candidates for the next module pair, not commitments.

## Who this is for

Graduate TAs and co-instructors with intermediate Python and basic networking. Embedded in education, learning-sciences, instructional-design, or AI-ethics courses — not CS security courses. The guide carries the structural and assessment work so the author can focus on pedagogy and course context.

## Use it

1. Open the [live guide](https://educatian.github.io/cybersentinel) and read the 90-minute worksheet (chapter 10).
2. Fork this repo into your course Git workspace.
3. Pick one row from the attack-surface table, one row from the ECD rubric, one parent template (T1–T7).
4. Customize the chosen template `.md` file.
5. Run it once yourself before students do.
6. Commit your customizations alongside the original — your fork becomes the institutional record.

## Important caveats

- Not a Pollen Robotics manual. Verify all device-specific commands against current SDK documentation before classroom use.
- Every exercise assumes an **isolated lab WiFi** controlled by the instructor and a signed **responsible-disclosure agreement** + **IRB protocol** before any student data is collected.
- Adversarial-robustness and prompt-injection results vary by model and conditions. Frame all such exercises as "characterize what happens when," not "demonstrate that X works."

## License

The guide content is intended for educational reuse within academic institutions. Attribute to the course's instructor of record and date the version used. Pull requests welcome from grad students improving any of the templates.

## Acknowledgments

Pedagogical structure draws on Mislevy, Steinberg & Almond's Evidence-Centered Design (2003); the OWASP IoT Top 10; and the AI-ethics teaching stack (Ethobot, AI Ethics Voyage, AIeL) maintained by [Educatian](https://github.com/Educatian).
