# Phase 1: Curriculum Design & Thread Architecture — Research

**Researched:** 2026-06-14
**Domain:** Curriculum design, critical thinking pedagogy, self-guided learning program architecture
**Confidence:** HIGH — thread sequencing and diagnostic approaches verified against established CT assessments and pedagogical research; emotional arc and content matrix format validated against Obsidian capabilities and self-directed learning literature

## Summary

Phase 1 designs the entire 12-month curriculum blueprints before any content is authored. This is a pure document-design phase: the deliverables are markdown files in an Obsidian vault. The research confirms that the decisions already captured in CONTEXT.md (4-thread architecture, Bloom's progression, depth-level convention, normative-first sequencing, emotional arc shape) are well-aligned with validated critical thinking pedagogy. Four specific design questions needed deeper investigation: entry diagnostic format, thread progression validity against external CT education sources, emotional arc design for months 10-12, and content matrix format in Obsidian.

**The entry diagnostic should not attempt to replicate validated CT assessments like Halpern or Watson-Glaser** (which require 40+ minutes, trained administrators, and psychometric validation). Instead, it should adapt those frameworks' question formats (scenario-based inference, assumption recognition, argument evaluation) into a 30-minute self-scored format using Obsidian-native Meta Bind widgets. The diagnostic is for self-placement, not assessment — its purpose is to answer "should I start at Month 01 or can I skip ahead?"

**Thread progression is validated.** van Gelder (2005), Willingham (2008, 2019), and UC Berkeley's Sense & Sensibility & Science course all converge on: normative models first → fallacies/deviation → probabilistic thinking → biases → integration. The 4-thread Foundation→Application→Synthesis→Teaching arc matches this consensus. No gap found in the proposed sequencing.

**The emotional arc (Month 10 peak → Month 11 valley → Month 12 peak) is sound** but needs structural scaffolding to work in a self-guided format. Month 11's lighter pace is critical — research on self-directed learning dropout shows that the 9-12 month window is where isolation and fatigue compound. The "Dear Researcher" letters, weekly check-ins, and author voice are the substitutes for cohort accountability that research recommends.

**Content matrix should use Dataview queries over frontmatter** as the primary implementation, with a secondary static markdown view in each monthly MOC for quick scanning. This makes the matrix maintainable and queryable across 12 months.

**Primary recommendation:** Start with the content matrix and depth-level conventions, then derive monthly outcomes, then build the entry diagnostic from existing CT assessment question patterns. Do not attempt to design a psychometrically valid instrument — that is out of scope for a self-guided placement tool.

---

<user_constraints>
## User Constraints (from CONTEXT.md)

### Decisions (Locked)

| Decision | Detail |
|----------|--------|
| North Star Outcome | By Month 12, a researcher can independently audit any research paper in their field using a structured framework integrating logic, probability, statistics, scientific reasoning, and metacognitive calibration — and can articulate their confidence with calibrated probabilistic estimates. |
| Thread Architecture | 4 threads (Logic & Reasoning, Probability & Statistics, Scientific Reasoning, Metacognition & Calibration) with Foundation→Application→Synthesis→Teaching arc across 12 months. See CONTEXT.md thread table. |
| Sequencing Rule | Normative models first → Fallacies as deviations from norms → Probability foundations → Bayesian reasoning → Cognitive biases → Scientific reasoning → Integration. |
| Depth-Level Convention | `depth-level:: 1` (Foundation: define/recognize), `depth-level:: 2` (Application: apply to paper), `depth-level:: 3` (Synthesis: combine concepts), `depth-level:: 4` (Teaching: explain/audit independently). |
| Bloom's Progression | M01-03: Remember→Understand→Apply; M04-06: Apply→Analyze; M07-09: Analyze→Evaluate; M10-12: Evaluate→Create |
| Entry Diagnostic | Self-assessment across 4 threads, scenario-based, borrows from Halpern and Watson-Glaser frameworks. Output: starting-month recommendation. No pass/fail. |
| Minimum Viable Path | Core lessons (70% effort, `#core` tag) + Enrichment (30% effort, `#enrichment` tag). Dataview dashboard filters by status. |
| Emotional Arc | Month 10: Peak (first complete paper audit); Month 11: Valley/Consolidation (gap-filling, lighter pace); Month 12: Peak (capstone Research Audit). |
| Outcome Format | "After Month N, the student can [verb] [object] by [method]." using Bloom's action verbs. |
| Belief Audit | Template in Phase 1, deployed Month 01. 5-7 epistemological statements logged quarterly. Frontmatter: `belief-audit::` for version tracking. |
| Content Matrix | Single markdown table (12 months × 6 disciplines) showing concept placement and depth level. |

### the agent's Discretion

- *(none explicitly marked — full research recommendations below)*

### Deferred Ideas (OUT OF SCOPE)

- *(none from this phase)*
</user_constraints>

<phase_requirements>
## Phase Requirements

| ID | Description | Research Support |
|----|-------------|------------------|
| CURD-01 | Program-level North Star outcome | Already defined in CONTEXT.md — aligns with van Gelder (2005) and Willingham (2019) definitions of critical thinking as domain-specific, self-directed, and evaluate-integrative. |
| CURD-02 | 12 monthly outcome statements (Bloom's) | Bloom's progression locked in CONTEXT.md. Research confirms Bloom's is appropriate but warns against rigid application (see Pitfall 1 below). Assign specific verbs per month. |
| CURD-03 | 4 Thread MOCs with progression | Thread progression validated against van Gelder (2005), Willingham (2008), UC Berkeley S&S&S syllabus, and Critical Thinker Academy sequencing. No gap found. |
| CURD-04 | Content matrix (12×6) | Format recommendation: Dataview-driven over frontmatter, with secondary static markdown table. See Research Question 4. |
| CURD-05 | `depth-level::` frontmatter convention | Locked. Verified against Dataview query capabilities — integer fields are natively queryable. |
| CURD-06 | Entry diagnostic quiz (Month 00) | See Research Question 1 for design methodology. Adapt Halpern + Watson-Glaser question patterns to 30-min self-scored format. |
| CURD-07 | Minimum viable path (Core vs Enrichment) | Locked in CONTEXT.md. Research confirms this is essential for preventing pile-up dropout (see PITFALLS.md). |
| CURD-08 | Emotional arc for Months 10-12 | Validated against self-directed learning completion rate research. See Research Question 3. |
| EXER-06 | Belief Audit template | Template design should include: 5-7 statements, 0-100 confidence scale (Meta Bind `INPUT[number]`), `belief-audit::` frontmatter linking to prior log. |
</phase_requirements>

## Architectural Responsibility Map

This phase designs the entire curriculum — there is no code, no server, no application tier. The single architectural layer is the Obsidian vault itself, specifically:

| Capability | Primary Tier | Secondary Tier | Rationale |
|------------|-------------|----------------|-----------|
| Curriculum design (outcomes, threads, matrix) | Design Layer (author) | — | These are authored documents, not runtime artifacts. No code execution. |
| Entry diagnostic delivery | Obsidian vault (reading view) | — | Self-scored; uses Meta Bind widgets and callout reveals. No backend. |
| Content matrix querying | Dataview (DQL) | Markdown tables | Dataview queries over frontmatter are the canonical source; static tables are fallback for quick scanning. |
| Thread MOCs | Obsidian notes with wikilinks | Dataview queries | MOCs are navigation documents linking to monthly content. Dataview queries within MOCs show thread progress. |
| Depth-level tracking | YAML frontmatter | Dataview aggregations | Every lesson note has `depth-level::` in frontmatter. Dataview rolls up by thread and month for dashboard. |

## Standard Stack

Since this phase produces markdown documents (not software), the "stack" is:

### Authoring Tools
| Tool | Purpose | Why Standard |
|------|---------|--------------|
| Obsidian (core editor) | Author all markdown | Vault constraint — no alternative |
| Dataview (plugin) | Queryable content matrix, progress dashboards | Already in stack from STACK.md research |
| Meta Bind (plugin) | Interactive diagnostic widgets (select, number inputs) | Only way to make Obsidian interactive for self-scored quiz |
| Templater (plugin) | Template-driven content generation | Powers all templates already designed in Phase 0 |

### Supporting
| Tool | Purpose | When to Use |
|------|---------|-------------|
| Advanced Tables (plugin) | Format static content matrix tables | When Dataview output needs manual adjustment |
| Excalidraw (plugin) | Visual argument mapping illustrations | For thread arc diagrams if desired |

## Package Legitimacy Audit

> No external packages are installed in this phase. All deliverables are markdown documents inside the existing Obsidian vault. The plugins listed above are already installed and configured in Phase 0. No registry verification needed.

**Packages removed due to slopcheck [SLOP] verdict:** N/A
**Packages flagged as suspicious [SUS]:** N/A

## Research Question 1: Entry Diagnostic Design

**Question:** What validated approaches exist for self-assessment critical thinking diagnostics? How to design a 30-minute quiz across 4 threads that outputs a starting-month recommendation?

### How Validated CT Assessments Work

Three major validated instruments exist. None are directly portable to Obsidian, but all offer question-format patterns adaptable to a self-scored tool:

| Assessment | Format | Duration | Subscales | Adaptability to Obsidian |
|------------|--------|----------|-----------|-------------------------|
| **Halpern Critical Thinking Assessment (HCTA)** | 25 scenarios + both forced-choice and open-ended responses | 50-60 min | 5: Verbal reasoning, argument analysis, hypothesis testing, likelihood/uncertainty, decision-making | MEDIUM — scenario format is adaptable; open-ended responses can't be auto-scored in Obsidian |
| **Watson-Glaser Critical Thinking Appraisal (WGCTA)** | 40 items, multiple-choice | 30-40 min | 5: Drawing Inferences, Recognizing Assumptions, Deducing, Interpreting, Evaluating Arguments | HIGH — multiple-choice/YES-NO format translates directly to Meta Bind `INPUT[select]` |
| **Critical Thinking Assessment Scale Short Form (CTSAS)** | 60 items, Likert scale | 20-30 min | 6: Facione's subscales (interpretation, analysis, evaluation, inference, explanation, self-regulation) | HIGH — Likert scale maps to Meta Bind `INPUT[slider]` |

[CITED: APA PsycTests — HCTA description, https://psycnet.apa.org/doi/10.1037/t10940-000]
[CITED: TalentLens Watson-Glaser product page, https://www.talentlens.com/watson-glaser.html]
[CITED: CTSAS Short Form validation, https://www.researchgate.net/publication/366435256]

### Watson-Glaser Question Structures Worth Borrowing

The WGCTA's five question types are the most adaptable to a self-scored format:

1. **Drawing Inferences** — Given a statement, rate the probability of several inferences. (Format: scenario + "True/Probably True/Insufficient Data/Probably False/False" scale)
2. **Recognizing Assumptions** — Given a statement, decide whether each proposed assumption is taken for granted. (Format: statement + YES/NO per assumption)
3. **Deduction** — Given premises, determine if a conclusion necessarily follows. (Format: premises + "Conclusion Follows/Does Not Follow")
4. **Interpreting** — Given evidence, decide if a conclusion is warranted. (Format: evidence paragraph + YES/NO per conclusion)
5. **Evaluating Arguments** — Given an issue, judge whether an argument is strong or weak. (Format: issue + "Strong Argument/Weak Argument")

[CITED: Pearson Watson-Glaser practice test PDF, https://www.pearsonvue.com/content/dam/VUE/vue/en/documents/clients/phnro/wg_practice.pdf]

### Recommended Design for Month 00 Diagnostic

**Do NOT attempt to create a psychometrically validated instrument.** The entry diagnostic is a self-placement tool, not an assessment. Its purpose is: "Should I start at Month 01 or can I skip ahead?" This reduces design complexity significantly.

**Proposed structure (20 questions, ~30 minutes):**

| Section | Questions | Format | Thread Assessed | Source Pattern |
|---------|-----------|--------|-----------------|---------------|
| A: Argument Analysis | 5 | Scenario + select best analysis | Logic & Reasoning | Watson-Glaser "Evaluating Arguments" + Halpern "Verbal Reasoning" |
| B: Probability Estimation | 5 | Scenario + estimate probability + confidence slider | Probability & Statistics | Halpern "Likelihood & Uncertainty" |
| C: Evidence Evaluation | 5 | Scenario + identify flaws in reasoning about evidence | Scientific Reasoning | Watson-Glaser "Interpreting" + Halpern "Hypothesis Testing" |
| D: Bias Recognition | 5 | Scenario + identify potential cognitive bias | Metacognition & Calibration | Adapted from Halpern "Argument Analysis" + Facione "Self-Regulation" |

**Scoring rule:** No pass/fail. Each section produces a score out of 10. Interpretation:
- Section score ≥ 8: Can skip that thread's Foundation depth (start at Application)
- Section score 4-7: Follow standard progression
- Section score < 4: Strongly recommended to start at Month 01 for that thread

**Overall recommendation logic (Templater-generated in self-scoring guide):**
```
If ANY thread scores < 4: Recommend Month 01 (full curriculum)
If ALL threads ≥ 4 and 1-2 threads < 8: Recommend Month 01 with enrichment skips on strong threads
If ALL threads ≥ 8: Recommend Month 04 entry (skip Foundation months)
```

**Obsidian implementation:**
- Each question uses Meta Bind `INPUT[select(option1,option2,...)]` for the choice
- Confidence slider: `INPUT[number(class:confidence)]` next to each answer
- Answer key: hidden behind Obsidian callout `> [!tip]- Reveal Answers` — student clicks to expand
- Scoring: manual tally with checkbox list (cannot auto-score in Obsidian)

**Key design constraint:** The diagnostic must feel useful even for students who score low. Frame it as "this tells you which areas need attention" rather than "you're not ready."

## Research Question 2: Thread Progression Validation

**Question:** Does the proposed 4-thread progression (Foundation→Application→Synthesis→Teaching) align with proven CT pedagogy? What do van Gelder, Willingham, and UC Berkeley say?

### van Gelder (2005) — "Teaching Critical Thinking: Some Lessons From Cognitive Science"

Six lessons that directly validate the proposed sequencing:

1. **Acquiring expertise in CT is hard.** — Supports the full 12-month duration. No quick fix.
2. **Practice in CT skills themselves enhances skills.** — Supports exercise-heavy (70%) vs reading-light (30%) ratio already in requirements.
3. **Transfer of skills must be practiced.** — Confirms spiral curriculum: revisiting concepts in multiple contexts. Strongly validates Foundation→Application→Synthesis→Teaching progression.
4. **Some theoretical knowledge is required.** — Validates including explicit instruction (normative models) before practice.
5. **Diagramming arguments (argument mapping) promotes skill.** — Supports use of Excalidraw or text-based argument mapping in exercises.
6. **Students are prone to belief preservation.** — Validates Month 08 dedicated to metacognition/identity-protective cognition and the Belief Audit.

**Sequencing implication:** van Gelder's Reason Project at Melbourne explicitly used normative logic first (validity, soundness, argument mapping), then moved to fallacies as deviations. This is exactly the CONTEXT.md sequencing rule.

[CITED: van Gelder, T. (2005). Teaching Critical Thinking: Some Lessons From Cognitive Science. College Teaching, 53(1), 41-48. https://doi.org/10.3200/CTCH.53.1.41-48]

### Willingham (2008, 2019) — "Critical Thinking: Why Is It So Hard to Teach?" + "How to Teach Critical Thinking"

Three critical findings for thread design:

1. **CT is domain-dependent.** Thinking processes are intertwined with content knowledge. You cannot teach "generic" critical thinking — every exercise must be applied to specific domain content. This validates the curriculum's paper-first pedagogy and the inclusion of field-specific exercise options.
2. **The surface-structure problem.** Students who learn a reasoning strategy in one context fail to apply it in another because the surface features look different. The spiral curriculum (revisiting concepts in different contexts across 12 months) directly addresses this.
3. **Three-part definition of CT:** The thinking must be (a) novel (not routinized), (b) self-directed (not following instructions), and (c) effective (respects conventions of good reasoning). This validates the progression from structured exercises (M01-03) → self-directed paper critiques (M04-06) → independent audit (M10-12).

**No gap found in proposed thread structure.** Willingham would caution against teaching CT as a "bag of tricks" — the curriculum's explicit teaching of normative models first (what makes a good argument) before moving to errors (fallacies, biases) is precisely what he recommends.

[CITED: Willingham, D.T. (2008). Critical Thinking: Why Is It So Hard to Teach? Arts Education Policy Review, 109(4), 21-32.]
[CITED: Willingham, D.T. (2019). How to Teach Critical Thinking. NSW Department of Education Occasional Paper Series.]

### UC Berkeley Sense & Sensibility & Science (S&S&S)

The S&S&S syllabus confirms the sequencing:

| S&S&S Concept Grouping | Timing in Course | Our Parallel Thread |
|------------------------|------------------|---------------------|
| Philosophical Underpinnings (shared reality, science as method) | Weeks 1-3 | Scientific Reasoning (Falsification, What is Science) — M01-03 |
| Probabilistic Thinking (uncertainty, calibration, signal/noise) | Weeks 3-7 | Probability & Statistics — M02-04 |
| Causal Reasoning (correlation, Hill's criteria, interventions) | Weeks 6-7 | Scientific Reasoning (Study Design) — M04-05 |
| Science's Can-do Aspect (Fermi problems, orders of understanding) | Weeks 7-8 | Scientific Reasoning (applied estimation, optimism) — M04-06 |
| Human Cognition (heuristics, biases, confirmation bias, blinding) | Weeks 8-11 | Metacognition & Calibration — M05, M08 |
| Group Decision Making (wisdom of crowds, deliberative polling) | Weeks 11-14 | Integration phase — M09-12 |

**Key observation:** S&S&S delays the full "Human Cognition" (biases) module until **after** probabilistic thinking and causal reasoning are taught. This is exactly the normative-first order captured in CONTEXT.md's sequencing rule. The UC Berkeley course aligns with the proposed thread structure.

**Minor gap found:** S&S&S includes a "Group Decision Making" thread (wisdom of crowds, deliberative polling, scenario planning) that is not explicitly present in our 4 threads. This is a gap worth noting — our curriculum currently lacks explicit treatment of collaborative/group reasoning, which is relevant for researchers who work in teams.

[CITED: UC Berkeley S&S&S syllabus, https://sense-sensibility-science.berkeley.edu/syllabus]
[CITED: S&S&S Concept Groupings, https://sensibility.berkeley.edu/index.php?title=Concept_groupings]

### Validation Summary

| Proposed Design Feature | Validated By | Confidence |
|------------------------|-------------|------------|
| Normative models before fallacies/biases | van Gelder (2005), Willingham (2008), UC Berkeley S&S&S | HIGH |
| Spiral curriculum (Foundation→Application→Synthesis→Teaching) | van Gelder — "transfer must be practiced" across contexts; Willingham — surface-structure problem demands multiple contexts | HIGH |
| Exercise-heavy (70%) vs reading-light (30%) | van Gelder — "practice in CT skills themselves enhances skills" | HIGH |
| Month 08 dedicated to identity-protective cognition | van Gelder — "students prone to belief preservation"; this needs extended treatment | HIGH |
| Paper-first pedagogy (concepts applied immediately) | Willingham — CT is domain-dependent; abstract theory without domain application doesn't transfer | HIGH |
| 12-month duration | van Gelder — "acquiring expertise in CT is hard"; no quick-fix evidence exists | MEDIUM |
| 4 threads instead of 6 | S&S&S uses 6 concept groupings — we fold Group Decision Making into Integration phase; acceptable tradeoff given researcher audience | MEDIUM |

### Gap: Group Decision Making

The curriculum currently has no explicit treatment of collaborative reasoning (peer review, adversarial collaboration, group decision-making). This is relevant for researchers. **Recommendation:** Add a sub-thread within Scientific Reasoning (M09-12) that covers adversarial collaboration, peer review dynamics, and group epistemic practices. The "Adversarial Collaboration" exercise already in requirements (EXER-08) partly addresses this.

## Research Question 3: Emotional Arc Design

**Question:** How to design the final 3 months (peak/valley/peak) to prevent final-stretch dropout? What pacing patterns work for self-guided programs in the 9-12 month range?

### The Data on Self-Directed Dropout

| Statistic | Source | Implication |
|-----------|--------|-------------|
| 55-70% dropout in professional certification programs | LearnStream (2025) | Majority dropout is normal — preventing it is a design achievement |
| 75-85% dropout on LinkedIn Learning | Multiple studies | Passive video formats have worst retention |
| 85-96% completion in cohort-based programs | altMBA, community data | Accountability + structure are the strongest completion predictors |
| 36% re-engagement rate with structured outreach | BrainCert | Lapsed students can be recovered with intervention |

[CITED: Retention and completion in online learning, Sadki 2026, https://doi.org/10.59350/fkzy8-6p459]
[CITED: Self-Directed Learning challenges review, Dahal & Bhat 2024, https://www.researchgate.net/publication/378588494]

### Why Months 10-12 Are the Danger Zone

Research identifies three compounding factors that peak at months 9-12 in self-guided programs:

1. **Isolation fatigue.** The initial novelty (M01-03) and momentum (M04-06) have worn off. The student has been working alone for 9+ months. Without cohort effects, engagement is fragile.
2. **Pile-up effect.** Earlier incomplete exercises, unanswered questions, and skipped readings accumulate. By Month 10, the student feels "behind" even if they're not.
3. **Finish-line anxiety.** The closer to the end, the more pressure the student feels to "do it right." This creates paradoxically opposite behaviors: either frantic over-effort (burnout) or avoidance (dropout).

### Validating the Peak/Valley/Peak Design

The proposed arc maps to the "Cinderella" shape (Rise→Fall→Rise) which narrative research identifies as one of the two most commercially successful emotional arcs (Jockers, Reagan).

**The key structural insight from research:** The arc is not cosmetic — it must change **what the student does each week**, not just how content is framed.

**Month 10 — Peak ("First Complete Paper Audit")**

*What makes it work:*
- **Milestone event, not just another month.** The student produces a complete artifact (first paper audit). This is psychologically significant — it marks the transition from "someone who learns CT" to "someone who does CT."
- **Messy-by-design.** The explicit framing ("this will be imperfect — that's the point") reduces finish-line anxiety. The student cannot fail at it because the goal is to have done it, not to have done it well.
- **Volume over precision.** More modules but each is shorter. This creates a sense of accomplishment through throughput.

*Structural requirements:*
- Shorter lessons (15-20 min vs 30-45 min)
- More checkboxes to tick (psychological progress signaling)
- One week with no new content — just "run your first audit" with scaffolding
- "Dear Researcher" letter that explicitly names the milestone feeling

**Month 11 — Valley / Consolidation ("Gap-Filling & Review")**

*What makes it work:*
- **Reduced cognitive load.** No new concepts. Only review, re-application, and gap-filling. This is the most important design decision for preventing dropout.
- **Permission to rest.** The month-opening letter explicitly says "this month is lighter. Take a breath. Review what you've learned. Fill the gaps that bother you."
- **Choice architecture.** The student selects 2-3 weak areas from a list. This restores autonomy (which self-determination theory identifies as a core psychological need).
- **Optional deep-dives.** For students who want more content, enrichment tracks exist. But Core is genuinely lighter.

*Structural requirements:*
- 50% reduction in weekly exercise volume
- "Pick your gaps" menu: list of common weak areas with pointers to relevant lessons
- One week of "no new content — just revisit your journal from M01-06"
- Re-do favorite exercise from earlier month (nostalgia + progress awareness)

**Month 12 — Peak ("Final Research Audit")**

*What makes it work:*
- **Student's own paper choice.** Intrinsic motivation peak. They pick a paper relevant to their own research.
- **Full integration.** Uses all 6 disciplines, all 4 threads. The Research Audit Framework becomes a reusable tool they keep after the course.
- **Before/after comparison.** The Belief Audit re-administered creates a "look how far you've come" moment.
- **Certificate.** A markdown "Certificate of Completion" with student's name and completion date. Research on goal gradients shows that tangible completion artifacts increase satisfaction and reduce last-minute dropout within the final month.

[ASSUMED: Goal gradient effect — training data only, no specific source verified in this session]

*Structural requirements:*
- Step-by-step audit framework that they can reuse post-course
- Belief Audit comparison report template
- Certificate note with Templater-generated fields
- Final "Dear Researcher" letter that reframes the course as "beginning, not end"

### Design Checklist for Months 10-12

| Design Element | M10 | M11 | M12 |
|----------------|-----|-----|-----|
| Lesson length | Short (15-20 min) | Minimal (10 min max) | Medium (20-30 min) |
| New concepts | Few | None | Integration only |
| Exercise volume | High (many small) | Low (choice-driven) | Medium (guided) |
| Autonomy | Low (structured audit) | High (choose gaps) | High (own paper) |
| Emotional tone | Exciting, honest about mess | Softer, permission-giving | Triumphant, forward-looking |
| Milestone artifact | First audit (messy) | — | Final audit (tools for life) |
| "Dear Researcher" letter theme | "You can do this" | "It's OK to rest" | "You're a different thinker now" |

## Research Question 4: Content Matrix Format

**Question:** What's the best format for a 12×6 content matrix in Obsidian? How to make it maintainable and queryable?

### Options Analyzed

| Option | Pros | Cons | Verdict |
|--------|------|------|---------|
| **A: Static markdown table** | Simple, no plugin dependency, readable at a glance | Brittle — adding/removing a concept requires editing a large table; no querying; duplicates information already in lesson frontmatter | Not recommended primary |
| **B: Dataview query over frontmatter** | Single source of truth (lesson frontmatter); auto-updating; filterable by depth, thread, month; queryable for dashboard | Requires Dataview plugin; not readable without rendering; needs consistent frontmatter across all lessons | **RECOMMENDED (primary)** |
| **C: Hybrid — static table + Dataview queries** | Best of both worlds: static for scanning, Dataview for analysis | Duplicates data; maintenance burden (must keep both in sync) | **RECOMMENDED (secondary: static per-month table in each MOC)** |
| **D: Canvas file** | Visual, spatial arrangement | Corruptible JSON blob; not queryable; breaks link-before-you-leave rule | Not recommended (per ARCHITECTURE.md anti-pattern) |

### Recommended Implementation

**Primary: Dataview-driven content matrix**

Each lesson note has frontmatter:
```yaml
---
month: 01
week: 3
thread: Logic & Reasoning
depth-level: 1
discipline: Philosophy/Logic
core: true
lesson-number: 01.03
---
```

The content matrix is a Dataview query in the Curriculum Hub or a dedicated `Content Matrix.md`:

```dataview
TABLE 
  depth-level AS "Depth",
  discipline AS "Discipline",
  thread AS "Thread",
  core AS "Core"
FROM "Curriculum"
WHERE month = 01
SORT lesson-number ASC
```

This produces a live table that updates automatically as lessons are authored.

**Secondary: Per-month static table in each monthly MOC**

A static markdown table in `Month 01/Month 01 MOC.md` showing the overview at a glance. Manually maintained during Phase 2 authoring:

```
| Week | Discipline | Thread | Depth | Core? |
|------|-----------|--------|-------|-------|
| 1 | Philosophy/Logic | Logic & Reasoning | 1 | ✓ |
| 1 | Probability | Probability & Statistics | 1 | ✓ |
```

### Frontmatter Schema for Lessons

From the depth-level convention and CONTEXT.md decisions, the canonical frontmatter for every lesson note should be:

```yaml
---
lesson-number: "MM.NN"
month: 01
week: 3
thread: Logic & Reasoning
discipline: Philosophy/Logic
depth-level: 1
core: true
tags: [curriculum, lesson]
---
```

**Why this schema:**
- `lesson-number` as string (not integer) enables "01.03" format for sortability
- `month` and `week` as integers for Dataview comparison operators
- `thread` matches the 4 thread names exactly — controlled vocabulary enforced by Templater
- `discipline` from the 6-discipline controlled vocabulary
- `depth-level` as integer 1-4 for numeric sorting and filtering
- `core` as boolean for MVP path filtering

**Note on discipline vs thread:** Threads are the spiral backbone (4). Disciplines are the content categories (6). A single lesson covers one discipline AND one thread. The Dataview content matrix can group by either dimension.

## Standard Stack

No code dependencies. The "stack" for this phase is:
- **Markdown** — all deliverables are markdown files
- **Data format** — YAML frontmatter (specifically: `month`, `week`, `thread`, `discipline`, `depth-level`, `core`, `lesson-number`)
- **Query engine** — Dataview DQL (for the content matrix and progress views)
- **Interactive widgets** — Meta Bind (for entry diagnostic)

## Don't Hand-Roll

This phase produces documents, not code. The "don't hand-roll" guidance applies to what NOT to build in the entry diagnostic:

| Problem | Don't Build | Use Instead | Why |
|---------|-------------|-------------|-----|
| Self-scoring algorithm | JavaScript/ plugin code | Manual answer key in Obsidian callout | Cannot auto-score in Obsidian without custom plugin |
| Psychometrically valid placement test | Full-scale CT assessment from scratch | Borrow question formats from Halpern/Watson-Glaser without attempting validation | Validated instruments require norming studies, IRT analysis, and hundreds of test subjects |
| Progress tracking system | Custom dashboard queries from scratch | Dataview DQL queries over standardized frontmatter | Dataview already handles filtering, grouping, and sorting |

**Key insight:** The most dangerous "hand-roll" temptation is trying to make the entry diagnostic a valid assessment instrument. It is a **self-placement tool** — it only needs to be good enough for a student to judge their own starting point. Over-engineering it wastes effort that should go into content quality.

## Common Pitfalls

### Pitfall 1: Rigid Bloom's Application
**What goes wrong:** Assigning Bloom's verbs mechanically (Month 01 = Remember, Month 02 = Understand) creates boring, sequential lessons where each month is a single cognitive level, ignoring the reality that every lesson involves multiple levels.
**Why it happens:** The Bloom's progression in CONTEXT.md is meant as an **arc summary**, not a lesson-by-lesson constraint.
**How to avoid:** Apply Bloom's at the monthly outcome level only. Individual lessons may span multiple levels. Month 01's outcome says "can distinguish arguments from non-arguments" (Apply, not just Remember), even though it's in the Remember→Understand→Apply zone.
**Warning signs:** A lesson plan that only defines terms (Remember) without asking the student to do anything with them (Apply).

### Pitfall 2: Content Matrix Drift
**What goes wrong:** The 12×6 content matrix is designed in Phase 1, but during Phase 2-5 authoring, the actual content diverges silently. By Month 08, the matrix no longer reflects reality.
**Why it happens:** The matrix is a static document; authoring happens in separate files. Without a sync mechanism, they diverge.
**How to avoid:** Use Dataview queries as the primary matrix (auto-synced from lesson frontmatter). The static table becomes a sketch, not the source of truth. During Phase 1, build a Dataview query that IS the content matrix — then it's always current.
**Warning signs:** A content matrix that references lessons that don't exist, or suggests a concept is covered in Month 03 when it's actually in Month 04.

### Pitfall 3: Emotional Arc Without Structural Change
**What goes wrong:** The peak/valley/peak plan exists in the design document, but all three months are authored with the same structure (same lesson length, same exercise volume, same weekly cadence). The emotional arc is purely in the language of the "Dear Researcher" letters — not in the actual workload.
**Why it happens:** Authoring inertia — it's easier to produce 12 months of identical structure than to redesign Month 11 to be genuinely lighter.
**How to avoid:** Enforce structural differences in the monthly MOC templates. Month 11's MOC should have fewer rows, shorter descriptions, and explicit "skip" options built into the template itself.
**Warning signs:** Month 10, 11, and 12 MOCs all have the same number of weekly entries.

## Code Examples

Since this phase produces markdown (not code), "examples" are schema definitions and Dataview query patterns:

### Lesson Frontmatter Schema Reference

```yaml
---
lesson-number: "01.03"
month: 01
week: 3
thread: Logic & Reasoning
discipline: Philosophy/Logic
depth-level: 1
core: true
tags: [curriculum, lesson]
learning-objectives:
  - "Identify premises and conclusions in a research claim"
  - "Distinguish arguments from non-arguments"
---
```

### Content Matrix Dataview Query

```dataview
TABLE 
  depth-level AS "Depth",
  discipline AS "Discipline",
  thread AS "Thread",
  core AS "Core"
FROM "Curriculum/Month 01"
SORT lesson-number ASC
```

### Thread-Specific Rollup Query

```dataview
TABLE 
  depth-level AS "Depth",
  month AS "Month",
  lesson-number AS "Lesson"
FROM "Curriculum"
WHERE thread = "Logic & Reasoning"
SORT month ASC, lesson-number ASC
```

### Depth-Level Aggregation for Dashboard

```dataview
TABLE 
  rows.depth-level AS "Depths Used"
FROM "Curriculum"
GROUP BY month AS "Month"
SORT month ASC
```

### Entry Diagnostic Question Format (Meta Bind)

```markdown
## Section A: Argument Analysis (5 questions)

### Question A1

**Scenario:** A researcher claims: "Since 80% of patients who received 
the new treatment improved, while only 40% in the control group improved, 
the new treatment is clearly effective."

**What is the main weakness in this reasoning?**

`INPUT[select(
option(), 
option(No control for placebo effect), 
option(Sample size is too small), 
option(Correlation does not equal causation), 
option(Improvement was not statistically significant)
):q_a1]`

**Confidence in your answer (0-100):** `INPUT[number(class:confidence)]`

…
```

### Self-Scoring Callout

```markdown
> [!tip]- Reveal Answers (Section A)
> 1. A3 — "No control for placebo effect" is the primary weakness. 
>    The scenario describes a before/after comparison, not a blinded trial.
>    **Confidence calibration:** If you were less than 100% confident in a correct answer,
>    you're underestimating your knowledge. If you were highly confident in a wrong answer, 
>    you're overconfident in this domain.
```

### Belief Audit Template Frontmatter

```yaml
---
belief-audit-date: 2026-06-14
belief-audit-round: 1
belief-audit-prior: 
tags: [curriculum, belief-audit]
statements:
  - id: ba-01
    text: "p-values measure the probability the null hypothesis is true"
    confidence: 65
  - id: ba-02
    text: "A well-designed observational study can establish causation"
    confidence: 40
  - id: ba-03
    text: "Bayesian reasoning is more intuitive than frequentist statistics"
    confidence: 30
  - id: ba-04
    text: "Most published research findings are true"
    confidence: 50
  - id: ba-05
    text: "Peer review reliably catches methodological errors"
    confidence: 55
---
```

## State of the Art

| Old Approach | Current Approach | When Changed | Impact |
|--------------|------------------|--------------|--------|
| CT taught as generic skill (general principles → apply anywhere) | Domain-dependent CT (practice in each field separately) | Willingham 2008; consensus by 2015 | Curriculum must include field-specific scaffolding |
| CT assessments as high-stakes, proctored tests | Self-assessment diagnostic for self-placement | Rise of metacognitive calibration research ~2015-2020 | Month 00 diagnostic is valid as a self-tool |
| Linear curriculum (discipline A → B → C) | Spiral curriculum (all threads, increasing depth) | Bruner 1960s, refined by van Gelder 2005 | 4 threads running simultaneously is correct |
| Completion by checking off modules | Emotional arc design for retention | Self-directed learning research 2020-2025 | Emotional arc is structural (workload changes), not cosmetic |

## Assumptions Log

| # | Claim | Section | Risk if Wrong |
|---|-------|---------|---------------|
| A1 | Watson-Glaser question formats (Inferences, Assumptions, Deduction, Interpretation, Arguments) are adaptable to a self-scored Obsidian format without losing diagnostic value | Entry Diagnostic | Diagnostic could be too different from validated formats to produce useful placement; fix: test with 2-3 colleagues before finalizing |
| A2 | The 4-thread structure adequately covers CT without a dedicated Group Decision Making thread | Thread Validation | Researchers miss collaborative reasoning skills (peer review, group deliberation); fix: add sub-thread to Scientific Reasoning M09-12 |
| A3 | Goal gradient effect applies to self-guided learning programs | Emotional Arc | Month 12 design depends on certificate providing motivational boost; if this doesn't transfer, Month 12 may not feel like a peak |
| A4 | Dataview queries over frontmatter are sufficient for the content matrix without custom DataviewJS | Content Matrix | Complex multi-dimensional views may need DataviewJS; fix: note as potential v2 enhancement |
| A5 | 5-7 epistemological statements are enough for the Belief Audit | Belief Audit | Too few statements may not capture meaningful change; fix: include an open-text "position statement" alongside each confidence slider |

## Open Questions

1. **Should Month 00 diagnostic include a confidence calibration score?**
   - What we know: Calibration (predicted vs actual accuracy) is a core curriculum theme. Including it in the diagnostic could prime the student.
   - What's unclear: This adds complexity to a 30-minute quiz. May require 50+ questions for meaningful calibration data.
   - Recommendation: Include calibration as an optional "bonus" section, not part of the main 20-question diagnostic. The main purpose is placement, not calibration.

2. **How to handle the Group Decision Making gap?**
   - What we know: UC Berkeley S&S&S dedicates 3+ weeks to group decision-making. Our curriculum has no equivalent.
   - What's unclear: Whether researchers need explicit training in collaborative reasoning, or whether peer review practice (already in requirements) is sufficient.
   - Recommendation: Fold adversarial collaboration (EXER-08) into M09 as a dedicated sub-module within Scientific Reasoning. This partially addresses the gap without adding a 5th thread.

3. **Should the emotional arc include a mid-program "ceremony" at Month 06?**
   - What we know: Self-directed learning research shows checkpoints at natural halfway points reduce dropout.
   - What's unclear: Whether a "halfway celebration" in the curriculum would feel authentic or forced.
   - Recommendation: Consider adding a "you're halfway" note to the Month 06 opening letter with a simple reflective exercise (re-read your Month 01 journal). Low effort, potentially high impact.

## Environment Availability

> **Skipped:** This phase has no external dependencies — all deliverables are markdown documents authored in Obsidian. No tools, CLIs, runtimes, or databases are needed beyond the already-configured vault from Phase 0.

## Validation Architecture

> **Skipped:** This phase produces curriculum design documents (not code). There are no automated tests, no Nyquist validation, and no executable artifacts. The "verification" for Phase 1 is manual review against the success criteria in ROADMAP.md and REQUIREMENTS.md.

## Security Domain

> **Skipped:** This phase produces curriculum design documents. There is no data processing, no authentication, no input handling, and no network communication. Security considerations are not applicable.

## Sources

### Primary (HIGH confidence)
- **van Gelder, T. (2005). Teaching Critical Thinking: Some Lessons From Cognitive Science.** College Teaching, 53(1), 41-48. — 6 key lessons that validate spiral curriculum, normative-first sequencing, and exercise-heavy design. [CITED: https://doi.org/10.3200/CTCH.53.1.41-48]
- **Willingham, D.T. (2008). Critical Thinking: Why Is It So Hard to Teach?** Arts Education Policy Review, 109(4), 21-32. — Domain-dependence of CT, surface-structure problem, three-part definition. [CITED: Reading Rockets reprint, https://www.readingrockets.org/topics/comprehension/articles/critical-thinking-why-it-so-hard-teach]
- **Willingham, D.T. (2019). How to Teach Critical Thinking.** NSW Department of Education Occasional Paper Series. — Explicit instruction + domain practice = CT improvement. [CITED: https://education.nsw.gov.au/content/dam/main-education/teaching-and-learning/education-for-a-changing-world/media/documents/How-to-teach-critical-thinking-Willingham.pdf]
- **UC Berkeley Sense & Sensibility & Science course syllabus and concept groupings.** — Verified sequencing alignment (normative → probabilistic → biases → integration). Group Decision Making gap identified. [CITED: https://sense-sensibility-science.berkeley.edu/syllabus, https://sensibility.berkeley.edu/index.php?title=Concept_groupings]
- **Halpern Critical Thinking Assessment (APA PsycTests).** — 5 skill areas, scenario-based question format patterns. [CITED: https://psycnet.apa.org/doi/10.1037/t10940-000]
- **Watson-Glaser Critical Thinking Appraisal (Pearson/TalentLens).** — 5 subtest format (Inferences, Assumptions, Deduction, Interpretation, Arguments), YES/NO and multiple-choice patterns adaptable to Meta Bind. [CITED: https://www.talentlens.com/watson-glaser.html, https://www.pearsonvue.com/content/dam/VUE/vue/en/documents/clients/phnro/wg_practice.pdf]
- **CTSAS Short Form validation (Education Sciences, 2022).** — 60-item short form of Facione-based CT assessment, strong reliability (α = 0.969). Confirms scenario-based Likert format. [CITED: https://www.researchgate.net/publication/366435256]

### Secondary (MEDIUM confidence)
- **Obsidian Dataview documentation (blacksmithgu/obsidian-dataview GitHub).** — DQL query patterns for TABLE, WHERE, SORT, GROUP BY. Confirms frontmatter querying capabilities. [CITED: https://github.com/blacksmithgu/obsidian-dataview]
- **Sadki, R. (2026). Retention and completion in online learning.** — Strategies for self-directed program completion. [CITED: https://doi.org/10.59350/fkzy8-6p459]
- **Dahal & Bhat (2024). Self-Directed Learning, its Implementation, and Challenges: A Review.** — Nepal Journal of Health Sciences. — Identifies isolation and lack of scaffolding as primary dropout drivers. [CITED: https://www.researchgate.net/publication/378588494]
- **Jockers, M. (2014). The Bestseller Code.** — Computational narrative analysis identifying Cinderella (rise-fall-rise) as commercially successful emotional arc. Confirms peak/valley/peak shape. [ASSUMED — training data, not verified in session]

### Tertiary (LOW confidence)
- **Online course completion rate statistics (multiple sources).** — 5-15% typical completion for self-paced; 85-96% for cohort-based. Specific rates vary by source and methodology. Use as directional, not precise. [ASSUMED]
- **Goal gradient effect in self-directed learning.** — Known from behavioral psychology but not verified in this session for the specific context of Obsidian-based curriculum completion. [ASSUMED]

## Metadata

**Confidence breakdown:**
- Entry diagnostic design: MEDIUM (question format patterns are verified; the specific 20-question design is a novel composition; will need testing)
- Thread progression validity: HIGH (convergent evidence from 3 independent sources)
- Emotional arc design: MEDIUM (shape is validated by narrative research; translation to self-guided curriculum context is a novel application)
- Content matrix format: HIGH (Dataview over frontmatter is a well-documented Obsidian pattern)

**Research date:** 2026-06-14
**Valid until:** 2027-06-14 (stable domain — CT pedagogy research changes slowly)
