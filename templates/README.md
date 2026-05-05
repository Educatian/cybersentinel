# Templates — Reachy Mini Cybersecurity Modules

These are the editable starter assets that accompany the [main guidebook](../index.html).

## What's here

| File | Use it when |
|------|-------------|
| `module_builder_worksheet.md` | You are authoring a new module (90 min, alone, with a timer) |
| `debrief_script.md` | You are about to run a 15-minute debrief at the end of any module |
| `ecd_evidence_rubric.md` | You are grading student artifacts |
| `lab_safety_checklist.md` | You are setting up the lab (semester start) or running a session (per class) |
| `irb_gate_checklist.md` | Before week 1 of any course using these modules |
| `T1_mitm_visible.md` | Authoring the visible-MITM beginner exercise |
| `T2_voice_prompt_injection.md` | Authoring the voice-prompt-injection beginner exercise |
| `T3_api_token_ctf.md` | Authoring the credential-exposure intermediate exercise |
| `T4_adversarial_patch.md` | Authoring the adversarial-vision intermediate exercise |
| `T5_dependency_confusion.md` | Authoring the supply-chain intermediate exercise |
| `T6_capstone_redblue.md` | Authoring the one-week red/blue capstone |
| `T7_defensive_engineering.md` | Authoring the two-week defense-engineering capstone |

## How to use

1. **Copy** the file into your course repo. Don't edit in place here.
2. **Customize** the bracketed fields for your course.
3. **Pin** the SDK version, dependency manifest, and lab WiFi config in your copy of the lab safety checklist.
4. **Iterate** — after each first run, edit your copy with what reality taught you and commit the diff.

## Suggested course repo layout

```
your-course-repo/
├── README.md
├── lab/
│   ├── safety_checklist.md       (copy of lab_safety_checklist.md)
│   ├── irb_gate.md               (copy of irb_gate_checklist.md)
│   └── reset_script.sh
├── rubric/
│   └── ecd_evidence_rubric.md
├── modules/
│   ├── 01_T1_mitm/
│   │   ├── README.md             (copy of T1_mitm_visible.md, customized)
│   │   ├── companion_code/
│   │   └── debrief.md            (copy of debrief_script.md, customized)
│   ├── 02_T3_token_ctf/
│   │   ├── README.md
│   │   └── companion_repo_template/
│   └── ...
└── debrief_notes/
    └── 2026-09-15_T1.md          (post-class TA notes)
```

## Notes

- These templates are practical scaffolding, not a complete curriculum. The pedagogy lives in your customization.
- All references to "current SDK" mean: verify against the version of the Reachy Mini SDK pinned in your virtualenv this semester. SDK surface evolves.
- The IRB gate is mandatory before any module runs with students whose data you intend to analyze. No exceptions.
