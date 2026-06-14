# Phase 1 Context — Curriculum Design & Thread Architecture

**Phase:** 1 of 7
**Goal:** The entire 12-month curriculum is designed at the outcome and thread level — what students learn, in what order, how depth progresses, and how to start.
**Mode:** mvp

## Auto-Resolved Decisions (from research)

### North Star Outcome
By Month 12, a researcher can independently audit any research paper in their field using a structured framework integrating logic, probability, statistics, scientific reasoning, and metacognitive calibration — and can articulate their confidence with calibrated probabilistic estimates.

### Thread Architecture (4 threads, spiral over 12 months)

| Thread | Foundation (M1-3) | Application (M4-6) | Synthesis (M7-9) | Teaching (M10-12) |
|--------|-------------------|--------------------|------------------|-------------------|
| Logic & Reasoning | Arguments, validity, fallacies | Formal logic in papers | Causal reasoning | Complete audit integration |
| Probability & Statistics | Probability intuition, conditional | Bayes theorem, calibration | Statistical critique | Research Audit Framework |
| Scientific Reasoning | What is science, falsification | Study design, confounds | Causal inference | Replication audit |
| Metacognition & Calibration | Confidence tracking, biases | Calibration practice, Brier scores | Identity-protective cognition | Belief audit before/after |

### Sequencing Rule
Normative models first → Fallacies as deviations from norms → Probability foundations → Bayesian reasoning → Cognitive biases → Scientific reasoning → Integration. This prevents superficial understanding from teaching biases before correct reasoning models.

### Depth-Level Convention
- `depth-level:: 1` — Foundation (define, recognize)
- `depth-level:: 2` — Application (apply to given paper)
- `depth-level:: 3` — Synthesis (combine multiple concepts)
- `depth-level:: 4` — Teaching (explain to peer, audit independently)

Used in frontmatter of every lesson note. Queried by Dataview for thread-progress dashboard.

### Bloom's Taxonomy Progression Across Months
- M01-03: Remember → Understand → Apply
- M04-06: Apply → Analyze
- M07-09: Analyze → Evaluate
- M10-12: Evaluate → Create (Research Audit)

### Entry Diagnostic (Month 00)
- Self-assessment across 4 threads with scenario-based questions
- Borrows from Halpern Critical Thinking Assessment and Watson-Glaser frameworks, adapted to the 4-thread structure
- Output: recommended starting month (Month 01 for full curriculum, or later month if student has strong prior knowledge)
- No pass/fail — purely for self-placement

### Minimum Viable Path
Each month defines Core lessons (required, ~70% of effort) and Enrichment lessons (optional deep-dives, ~30%).
- Core: marked with `#core` tag in monthly MOC
- Enrichment: marked with `#enrichment` tag
- Dataview dashboard filters by status so students see progress on Core only

### Emotional Arc (Months 10-12)
- Month 10: Peak (first complete paper audit — exciting but messy, builds confidence through doing)
- Month 11: Valley / Consolidation (gap-filling, lighter pace, revisit weak areas — prevents final-stretch burnout)
- Month 12: Peak (capstone Research Audit — polished, integrated, student's own paper choice)

### Outcome Statements Format
Each month has a single outcome statement using Bloom's taxonomy action verb:
`"After Month N, the student can [verb] [object] by [method]."`
Examples:
- Month 01: "After Month 01, the student can distinguish arguments from non-arguments by identifying premises and conclusions in a research claim."
- Month 12: "After Month 12, the student can independently audit a research paper from their field using a structured framework that evaluates the claim, evidence, methodology, reasoning chain, and author biases."

### Belief Audit
- Template created in Phase 1, deployed in Month 01
- Students log positions on 5-7 key epistemological statements (e.g., "p-values measure the probability the null hypothesis is true")
- Revisited quarterly (Month 03, 06, 09) and final comparison in Month 12
- Frontmatter: `belief-audit:: [[link-to-prior-log]]` for version tracking

### Content Matrix File
Single markdown table (12 months × 6 disciplines) showing which concepts appear when and at what depth level. Updated if scope changes. Used to verify no orphan depth-levels and no concept gaps.

## Deferred Ideas
- *(none from this phase)*

## Next
Plan and execute this phase.
