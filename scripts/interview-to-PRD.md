# Script: Interview to PRD (Full Pipeline)

## Purpose
Run the complete research-to-product pipeline in a single pass — no human intervention required between steps. This script chains interview analysis and PRD writing end-to-end.

---

## Execution Rules

- Run all steps sequentially without stopping, asking questions, or waiting for confirmation
- Never ask the user to review, approve, or choose anything between steps
- If information is missing or ambiguous, make a reasonable decision and document it in the output file — do not pause
- Do not summarize progress or ask if you should continue — just proceed

---

## Instructions

### Step 1 — Run Interview Analysis

Execute the full instructions in `scripts/interview-analysis.md` exactly as written:

1. Read all interview files in `input/`
2. Launch one parallel agent per interview file, each producing a deep individual analysis
3. Save each individual analysis to `output/interview-individual-[lastname]-[YYYY-MM-DD].md`
4. Once all individual agents complete, synthesize across all individual analyses
5. Save the synthesis to `output/interview-synthesis-[YYYY-MM-DD].md`

Do not proceed to Step 2 until all output files from Step 1 are written and confirmed.

---

### Step 2 — Run PRD Writer

Execute the full instructions in `scripts/PRD-writer.md` exactly as written, using:

- `context/company.md`
- `context/strategy.md`
- The synthesis file just created in Step 1: `output/interview-synthesis-[YYYY-MM-DD].md`

Derive the product proposal, fill every section of the PRD template, and save the completed PRD to:
`output/PRD-[product-name]-[YYYY-MM-DD].md`

Do not proceed to Step 3 until the PRD file from Step 2 is written and confirmed.

---

### Step 3 — Build HTML Prototype and Open in Browser

Read the PRD just created. Identify the single most obvious, immediately sellable core interaction — the one thing a stakeholder could click on in 30 seconds and instantly understand the value.

Build a self-contained HTML file that demonstrates that interaction. Requirements:

- Single `.html` file, no external dependencies (inline all CSS and JS)
- Focused on the one key flow — not a full product, not a dashboard with every feature
- Realistic enough to feel real: use plausible placeholder data drawn from the interview context
- Clean, simple visual design — looks intentional, not like a wireframe
- Must be interactive: at minimum one button, input, or action that shows the core value
- No lorem ipsum. All copy should reflect the actual product and user context.

Save the prototype to:
`output/prototype-[product-name]-[YYYY-MM-DD].html`

Then open it in the default browser by running:
`open output/prototype-[product-name]-[YYYY-MM-DD].html`

---

## Output Files (in order of creation)

1. `output/interview-individual-[lastname]-[YYYY-MM-DD].md` — one per interviewee
2. `output/interview-synthesis-[YYYY-MM-DD].md` — cross-interview synthesis
3. `output/PRD-[product-name]-[YYYY-MM-DD].md` — completed PRD
4. `output/prototype-[product-name]-[YYYY-MM-DD].html` — interactive HTML prototype

Do not include these script instructions in any output file.
