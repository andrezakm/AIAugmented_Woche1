# Script: Interview Analysis

## Purpose
Analyze a set of qualitative interview files and produce two outputs:
1. A deep individual analysis file for each interview
2. A synthesis file combining all individual analyses into cross-interview findings

---

## Inputs
- All interview files located in the `input/` folder
- Read the full list of interview files before starting

---

## Instructions

### Step 1 — Spin Out Parallel Agents (one per interview file)

For each interview file found in `input/`, launch a separate agent in parallel. Each agent receives exactly one interview file and must produce a deep individual analysis of that single interview.

Each individual agent must cover:

**1. Interviewee Profile**
- Name, role, date of interview
- One paragraph characterizing who this person is in the organization and what lens they see the world through

**2. Sentiment**
- Dominant emotional tone (be specific — not just "frustrated" but what flavor and why)
- Energy level: are they burnt out, charged up, resigned, defensive?
- Trust level: do they trust their tools, their colleagues, their leadership?
- One direct quote that best captures their emotional state

**3. Problems They Described**
- List every problem they mentioned, direct or implied
- For each: what is it, how did they describe it, how much pain did they express around it?

**4. Urgency Signals**
- Which problems did they flag as urgent, pressing, or costing them right now?
- Look for language like "right now", "every day", "I can't", "it's killing us", numbers and metrics, emotional intensity spikes

**5. Underlying Needs**
- What does this person actually need in order to do their job well?
- State each need as: "This person needs X so that Y"
- Distinguish between what they said they want vs. what they actually need

**6. Notable Quotes**
- 3–5 direct quotes that are vivid, specific, or particularly revealing

Save each individual analysis to:
`output/interview-individual-[interviewee-lastname]-[YYYY-MM-DD].md`

---

### Step 2 — Synthesize Across All Individual Analyses

Once all individual agents have completed, read all individual output files and produce a single synthesis document.

The synthesis must cover:

**1. Sentiment Across the Group**
- Table: Interviewee | Role | Dominant Sentiment
- Overall paragraph: What is the emotional climate of this organization? Are there patterns across levels (leadership vs. ground-level)? Who is an outlier and why?

**2. Main Problems (cross-interview)**
- Group and consolidate problems that appear across multiple interviews
- For each consolidated problem: name it, describe it, list which interviewees mentioned it and how
- Rank by frequency (how many people mentioned it) and depth (how much pain it caused)

**3. Urgent Problems**
- From the consolidated list, identify only those with direct, measurable impact right now
- Explain what is being lost or degraded today as a result
- Reference specific evidence from specific interviewees

**4. High-Level Summary**
- 2–3 paragraphs maximum
- Answer: What is the single root cause? What would the highest-leverage intervention be?
- Be direct. No hedging. Speak from the evidence.

Save the synthesis to:
`output/interview-synthesis-[YYYY-MM-DD].md`

---

## Output Files
- One file per interviewee: `output/interview-individual-[lastname]-[YYYY-MM-DD].md`
- One synthesis file: `output/interview-synthesis-[YYYY-MM-DD].md`
- Do not include these script instructions in any output file
