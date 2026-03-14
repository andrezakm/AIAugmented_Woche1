# Script: PRD Writer

## Purpose
Produce a Product Requirements Document (PRD) for a product proposal grounded in real interview evidence. Every run of this script must result in a PRD that reflects:
- NeoEmployee's company identity and business model (`context/company.md`)
- NeoEmployee's current strategy and constraints (`context/strategy.md`)
- The most recent interview synthesis (`output/interview-synthesis-[latest-date].md`)

---

## Inputs

Load and read the following files before writing anything:

1. `context/company.md` — Who NeoEmployee is, what we build, how we work
2. `context/strategy.md` — Bootstrap phase, T&M model, path to products, constraints
3. `output/interview-synthesis-[latest-date].md` — Cross-interview findings: sentiment, main problems, urgent problems, high-level summary

---

## Instructions

### Step 1 — Derive the Product Proposal

Before writing the PRD, answer these questions internally:

**From the interview synthesis:**
- What is the single root cause identified?
- What are the urgent problems with the clearest, most immediate revenue impact?
- What is the highest-leverage intervention described?

**From the company context:**
- Which skill or set of skills would this product replace or augment?
- Is this aligned with NeoEmployee's vision of replacing employee skills with AI agents?

**From the strategy context:**
- Is this deliverable on a T&M basis with a short engagement timeline? (Bootstrap constraint: we need revenue fast.)
- Is this a pattern likely to repeat across other clients, making it a candidate for future productization?
- Does this qualify under the vision filter?

Select the product that scores highest on: urgency of the problem, clarity of the ROI, speed to deliver, and fit with the vision. Prefer the quick fix over the comprehensive solution. NeoEmployee needs wins that generate revenue in weeks, not months.

---

### Step 2 — Write the PRD

Fill in every section of the PRD template below. Do not leave any section empty. If a section requires information not yet available (e.g., specific milestone dates), use relative timing (Week 1, Week 2, etc.) and flag it for the client to confirm.

---

## PRD Template

```
# PRD: [Product Name]

**Prepared by:** NeoEmployee
**Date:** [today's date]
**Based on:** Interview research — [number] interviews, [date range]
**Engagement type:** Time & Material / Custom AI Agent Build

---

# Problem Alignment

## Problem & Opportunity

[1–2 sentences. Must be readable standalone and communicable to a non-technical stakeholder.]

- Why does this matter to the customer and to NeoEmployee?
- What evidence from the interviews supports this? (Quote or cite specific interviewees.)
- Which roles and people are most affected?
- Why is solving this urgent — what is being lost every day it goes unsolved?
- Why now — what makes the timing right?

## High-Level Approach

[Describe the rough shape of the solution. One clear sentence that captures it. Then explain why this approach over alternatives.]

**Alternatives considered:**
- [Alternative 1] — why we ruled it out
- [Alternative 2] — why we ruled it out

### Narrative

[Write a brief story — one day in the life of the primary user before the agent, and one day after. Make the contrast concrete and human.]

## Goals

1. [Primary measurable goal — tied to the urgent problem]
2. [Secondary measurable goal]
3. [Qualitative/feeling goal — what should the user experience feel like?]
4. [Guardrail metric — what should NOT get worse]

## Non-Goals

1. [What this agent explicitly does not do — and why]
2. [What is out of scope for this engagement]
3. [What is saved for a future phase or product]

---

# Solution Alignment

## Key Features

**Plan of record (MVP):**

1. [Feature 1 — most critical, must-ship]
2. [Feature 2]
3. [Feature 3]
4. [Feature 4]

**Future considerations:**

1. [Feature saved for Phase 2]
2. [Feature saved for Phase 2]

### Key Flows

[Describe the end-to-end experience as numbered steps. What does the user do? What does the agent do? What lands in their hands?]

1. ...
2. ...
3. ...

### Key Logic

1. [Rule 1 — how the agent decides what to surface]
2. [Rule 2 — formatting or length constraints on output]
3. [Rule 3 — how conflicts or missing data are handled]
4. [Rule 4 — what the agent does NOT overwrite or touch]
5. [Non-functional requirement — performance, latency, reliability]

---

# Development and Launch Planning

| Milestone | Target | Description |
|-----------|--------|-------------|
| Kickoff | Week 1 | Scope confirmation, data source access, CRM credentials |
| Agent prototype | Week 2–3 | First working version on 20 test prospects |
| Client feedback round | Week 3 | Rep team tests prototype, feedback collected |
| Integration complete | Week 4–5 | CRM write-back, delivery mechanism live |
| QA & edge case hardening | Week 5–6 | Edge cases, formatting, error handling |
| Launch | Week 6 | Full prospect list live, all reps onboarded |

## Operational Checklist

- [ ] CRM credentials and API access confirmed
- [ ] Prospect list format agreed (CSV / CRM export / live sync)
- [ ] Output delivery method confirmed (email digest / CRM attachment / Slack)
- [ ] Data sources and scraping permissions reviewed
- [ ] Rep team onboarding session scheduled
- [ ] Success metrics baseline captured before launch
- [ ] Rollback / pause plan documented

---

## Other

### Risks

1. [Risk 1 — data source reliability or access]
2. [Risk 2 — CRM integration complexity]
3. [Risk 3 — rep adoption]

### FAQ

**Q: Why not just buy more ZoomInfo licenses?**
A: [Answer grounded in interview evidence]

**Q: How is this different from what the SDRs are doing today?**
A: [Answer grounded in interview evidence]

### Appendix

- Interview synthesis: `output/interview-synthesis-[date].md`
- Individual interview analyses: `output/interview-individual-*-[date].md`
- Company context: `context/company.md`
- Strategy context: `context/strategy.md`

---

## Product Summary

[Write 1 tight paragraph — maximum 5 sentences — that describes the product at the highest possible level. What is it, who is it for, what does it replace, what does it deliver, and what changes for the user the day it goes live. This paragraph should be readable by a CEO, a sales rep, or an investor in 30 seconds and leave them with a complete picture.]
```

---

## Output

Save the completed PRD to:
`output/PRD-[product-name]-[YYYY-MM-DD].md`

Do not include these script instructions in the output file.
