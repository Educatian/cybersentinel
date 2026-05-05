# IRB & Consent Gate

> Treat the lab WiFi as an instrument under IRB scope. The fact that you control the router does not change the consent question.

---

## Before week 1

- [ ] **IRB protocol amendment filed.** Names the Reachy Mini exercises, data captured, and storage plan.
- [ ] **Written informed consent** distributed and signed. One page. Plain language.
- [ ] **Responsible-disclosure agreement** signed by every student.
- [ ] **Data-minimization plan** documented. Default: no audio of student voices, no video of student faces, no keystroke logging. Justify exceptions in writing.
- [ ] **Department legal contact** has reviewed the disclosure agreement language once.

---

## Draft consent paragraph (adapt to your IRB)

> *"This course includes hands-on cybersecurity exercises using a small networked robot in an isolated classroom lab. During each exercise, the instructor's laptop will capture network traffic between your laptop and the robot, and you will produce written reflections and short code submissions. Participation in the exercises is required for the course. Participation in the optional research study (which may use de-identified copies of your reflections, code, and packet captures to study how students learn cybersecurity concepts) is **not** required and will not affect your grade. You can opt out of the research at any time, including after the course ends, by contacting [PI name and email]. No audio of your voice, no video of your face, and no keystroke data will be collected. Captures will be retained on a department-managed drive for [X] years and then deleted.*
>
> *I understand the above and consent to participate in the research study (please initial): _____*"

Customize the bracketed fields and have your IRB office approve before distributing.

---

## Per-session

- [ ] Lab WiFi confirmed isolated (phone test)
- [ ] Camera shutter closed until needed
- [ ] Responsible-disclosure reminder spoken aloud
- [ ] Stop-word announced at start: **"_____________"** (pick one and use it all semester)
- [ ] Stop-word honored without follow-up questions if invoked

---

## Per-session post-class

- [ ] Tokens issued during class revoked
- [ ] Captures moved off student devices to course storage
- [ ] Lab WiFi password rotated *if* a token leaked beyond the lab repo
- [ ] One-paragraph incident note written

---

## When something goes wrong

If a student raises a concern (during or after class):
1. **Listen first.** Do not problem-solve while they are still describing what bothered them.
2. **Document the concern** in your TA notes within 24h.
3. **Notify the IRB office** within 5 business days if the concern involves a possible protocol deviation.
4. **Adjust the next session** if the concern reveals a real gap — not just to be defensive.

If a student reports they were tempted to use a learned technique outside the lab:
1. Re-state the responsible-disclosure agreement, in writing if possible.
2. Offer to help them write a responsible disclosure if they noticed something real in a deployed product they own.
3. Document the conversation.

---

## Hard rules

- No collection of voice or face data unless the IRB protocol explicitly approves it.
- No exercise touches a network or device outside the lab WiFi. No exceptions.
- No technique is demonstrated against a third-party service without that service's written authorization.
- The "stop word" cannot be vetoed. If invoked, the exercise pauses and the student does not have to explain.
