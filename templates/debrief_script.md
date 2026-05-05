# Debrief Script Template

> Run after every Reachy Mini cybersecurity exercise. ~15 minutes. TA leads, writes responses on shared board.

---

## Setup (1 min)

- Bring up a shared board (whiteboard or shared doc)
- Three columns: **Technical** · **Design** · **Transfer**
- Remind students: "There are no wrong answers in a debrief. We're describing what happened, not who won."

---

## Tier 1 — Technical (5 min)

Goal: rebuild a shared timeline of what actually occurred.

1. "Walk me through what you actually did, in order."
2. "Show me the moment the behavior changed. What command, what frame, what input?"
3. "What was the smallest piece of information that made the rest possible?"

Listen for: students attributing causation to the wrong layer (e.g., blaming the script when the channel was at fault).

---

## Tier 2 — Design (5 min)

Goal: surface the assumption that broke.

1. "What assumption was the system making about its environment that turned out to be wrong?"
2. "If you were the engineer who built this, what would you change first? What would you change second?"
3. "What would your fix cost — in latency, user experience, development time, money?"

Listen for: "just add encryption" answers without naming the cost. Push back gently.

---

## Tier 3 — Transfer (5 min)

Goal: move the lesson out of the lab.

1. "Where in your everyday life have you used a system that probably has this same weakness?"
2. "What would responsible behavior look like if you discovered this weakness in a deployed product tomorrow?"
3. "What does this exercise tell you about the limits of your own ability to assess AI risk?"

Listen for: a student who answers "I'd report it" without naming who, how, or what they'd say if ignored.

---

## Silent close (2 min)

Hand each student an index card. Prompt:

> "What is one thing you are now less sure of than you were an hour ago?"

Two minutes silent writing. Collect the cards. Do not grade them — read them.

---

## TA notes (post-class, 5 min)

- One sentence: what surprised me about this debrief?
- One sentence: what should the next instance of this module change?
- File this in the course repo under `debrief_notes/<date>_<module>.md`.

---

## When the debrief goes flat

If the room stays silent past 30 seconds on a Tier 1 question:
- Drop to a more concrete prompt: "Group 2, what was on your screen at minute 14?"

If the room stays silent on Tier 2:
- Show the relevant slide from your lecture and ask "which assumption on this slide was the one that broke?"

If the room stays silent on Tier 3:
- Volunteer your own example first: "Last month I noticed my home thermostat..."

Silence on Tier 3 most often means students are ethically uncomfortable, not bored. Acknowledge that explicitly: "It's okay if this question feels heavy. Take a minute."
