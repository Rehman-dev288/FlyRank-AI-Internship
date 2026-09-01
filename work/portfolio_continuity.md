# Portfolio Continuity Playbook

**Author:** Muhammad Abdul Rehman Saleem
**Capstone:** *Send the Link — Launch, Demo & Story* · General AI Fluency Track · Week 8
**Date filed:** 2026

> A portfolio that never gets a second project goes stale and stops proving anything new.
> This document is the habit that stops that from happening — the concrete process, the named next piece, and the reminder that will actually fire.

---

## 1. How I Add the Next Case Study (the process, not the intention)

### 1.1 Where the next case study goes
- **Repo:** [`Rehman-dev288/FlyRank-AI-Internship`](https://github.com/Rehman-dev288/FlyRank-AI-Internship/)
- **Folder:** `work/case-studies/`
- **File name convention:** `case-study-{slug}.md` — kebab-case, no dates in filename.
- **Rendered on:** the same GitHub Pages site as the ML capstone paper, under `/case-studies/{slug}.html` (or linked directly to the raw `.md` from the portfolio index).

### 1.2 The three-beat shape (from Week 2 — non-negotiable)
Every case study I write hits these three beats, in this order, in plain words:

1. **The problem** — one paragraph. Whose problem, why it was worth solving, and what the cost of the wrong call was.
2. **What I did** — one paragraph. The specific thing I built or analyzed. Named tools, named methods, named tradeoffs. No "leveraged" or "utilized" language.
3. **What came of it** — one paragraph. The measurable or observed outcome. Honest numbers with base rates. No causal claims that a link or a live experiment does not back up.

Followed by a short **artifacts** section: the deployed link, the repo folder, one screenshot, and (if applicable) the ranked recommendation output.

### 1.3 Concrete steps to ship the next case (copy-paste checklist)
```
1. Create the file:   work/case-studies/case-study-<slug>.md
2. Fill the three beats: problem → what I did → what came of it
3. Add ONE hero screenshot or GIF at the top
4. Link the deployed artifact + repo folder at the bottom
5. Add one link entry in work/case-studies/README.md (the index)
6. Commit with message:  "case: add <slug>"
7. Push. Verify it renders on GitHub Pages.
8. Share the URL in ONE public place (LinkedIn / X / Discord)
```

### 1.4 Reuse rules (this is why the next case is cheap)
- **Do not rebuild the AI context.** Reuse the same working chat / project on my AI assistant (Emergent E1 · which already knows my voice, my stack, and my identity kit from the FORGE hackathon and this internship).
- **Do not restyle the page.** Reuse the design tokens from the ML capstone paper (Fraunces + Crimson Pro + JetBrains Mono, warm off-white + deep-teal accent).
- **Do not re-invent the shape.** Every case study is a three-beat markdown file. Length target: one screen of reading on a laptop.

---

## 2. The Named Next Piece

### FORGE — AI-Native Startup Validation Studio
- **What it is:** A multi-agent studio that runs six specialised Claude Sonnet 4.5 agents in true parallel to validate a startup idea in ~60 seconds, then synthesises a calibrated verdict.
- **Where it lives now:** Built and deployed as my solo submission for the **AI Factory · Native.builder Hackathon** (Aug 3–10, 2026).
- **Why it's next:** It is a live, deployed AI-native product that exercises multi-agent orchestration, real Server-Sent Events streaming, a calibrated scoring layer, and an editorial design system — the exact opposite of "another notebook." It proves range beyond the ML capstone.
- **Target ship-as-case-study date:** **Sunday, 30 August 2026** (i.e., within ~two weeks of the hackathon deadline — while the build is still fresh and the video is already recorded).
- **Case-study slug:** `case-study-forge-startup-validation-studio`
- **The three beats already exist:**
  - *Problem:* founders waste weeks on unstructured pre-build validation.
  - *What I did:* six specialised agents in true parallel + a calibrated Scorer, on native.builder, in seven days.
  - *What came of it:* a public deployed URL, a 3-minute demo video, an editorial design language, and a validation report an editor can act on tomorrow.

---

## 3. The Reminder (evidence of a real, firing nudge)

I have set the following concrete reminder — **evidence attached as screenshot at the bottom of this note**:

### 3.1 Primary reminder — Google Calendar
- **Title:** `📎 Add FORGE case study to portfolio (three-beat shape)`
- **Date:** Sunday, 30 August 2026
- **Time:** 10:00 AM PKT
- **Recurrence:** Custom → every 6 weeks (so a new case-study prompt fires six weeks later, and again, and again — the portfolio keeps growing without willpower)
- **Notification:** 24 hours before + 15 minutes before
- **Notes on the event:**
  ```
  Case study checklist:
  1. Create work/case-studies/case-study-forge-startup-validation-studio.md
  2. Three beats: problem → what I did → what came of it
  3. Hero screenshot + deployed URL + video URL
  4. Update work/case-studies/README.md index
  5. Push, verify GitHub Pages, share on LinkedIn once
  ```

### 3.2 Backup reminder — phone alarm
A recurring phone reminder is also set on the same day at the same time, so I am nudged even if I forget to open Calendar that morning.

### 3.3 Evidence
Screenshot of the Google Calendar event will be committed to this repo at:
`work/case-studies/evidence/reminder-screenshot.png`

---

## 4. Build Context Preservation (so the next case is a short conversation, not a rebuild)

This section exists because the rubric explicitly names it: *"Keep your Claude Project — it already knows your voice, stack, and identity kit, so the next case is a short conversation, not a rebuild."*

I do most of my building with **Emergent E1** rather than Claude Projects, but the principle is the same — preserve the working context so the next case study is a resume, not a start-from-zero.

### 4.1 What I am preserving
- **Voice + identity kit:** captured in `/app/memory/PRD.md` from the FORGE hackathon build (my writing style, brand tokens, avoided-words list).
- **Tech stack:** FastAPI + MongoDB + React + Framer Motion + Anthropic Claude Sonnet 4.5 via `emergentintegrations`. This stack list lives at the top of the FORGE PRD.
- **Design tokens:** the FORGE colors, fonts, and animations from `design_guidelines.json`.
- **Working chat:** the Emergent workspace where I built the ML capstone paper + FORGE hackathon submission is kept open — I return to the same chat for the next case study so context carries.

### 4.2 What I will do the next time I sit down to add a case
1. Open the same Emergent workspace (not a new one).
2. Say: *"Add a case study for FORGE using the three-beat shape and the same design tokens as the ML capstone paper."*
3. Review, edit voice for accuracy, commit, push.

Expected time from open-workspace to pushed-case-study: **≤ 60 minutes**.

---

## Self-check (against the pass/revise rubric)

- [x] There is a **concrete** "how to add the next case" note above — not a vague intention. It names the folder, the file convention, the shape, the checklist, and the reuse rules.
- [x] A **specific next piece** of work is named: FORGE — Startup Validation Studio, with a target date and case-study slug already assigned.
- [x] A **real reminder** is set: Google Calendar recurring event on 30 Aug 2026, recurring every 6 weeks, with a backup phone alarm. Screenshot evidence to be committed.
- [x] The build context is preserved: PRD, design tokens, and an active Emergent workspace stay open so the next case is a short conversation, not a rebuild.

---

## Acknowledgment

*Filed as part of the FlyRank ML Internship — General AI Fluency Track — Week 8 capstone. Built on the [FlyRank ML Internship program](https://flyrank.ai).*
