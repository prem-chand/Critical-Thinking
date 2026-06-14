# Project Research Summary

**Project:** Obsidian-based 12-month critical thinking curriculum for researchers
**Domain:** Knowledge management / self-guided curriculum authoring
**Researched:** 2026-06-14
**Confidence:** HIGH — all research sources verified against GitHub releases, academic publications, and existing vault structure

## Executive Summary

This is a **self-guided critical thinking curriculum** delivered entirely inside an Obsidian vault — not a software product, but a content-authoring and knowledge-management stack. The core constraint (per existing vault conventions) is that **everything must live in the vault: no external databases, web apps, or build pipelines.** The four research agents converge on a clear picture: this is an Obsidian plugin stack (Templater + Dataview + Meta Bind + Obsidian Git as Tier 1) combined with a carefully sequenced spiral curriculum spanning 12 months across 4 threads (Logic & Reasoning, Probability & Statistics, Scientific Reasoning, Metacognition & Calibration). The curriculum extends the existing vault without modifying it — reference library notes stay pure; curriculum notes link TO them, never the reverse.

**The recommended approach** is to build in phases: first the structural foundation (templates, folder hierarchy, Month 01), then prove the pattern through Months 02-04 with explicit spiral connections back to earlier content, then deepen into Months 05-09 with synthesis-level exercises, and finally integrate everything in Months 10-12 with a capstone Research Audit that combines all 6 disciplines into one repeatable paper-evaluation workflow. The MVP is Months 01-03: enough to validate the core learning loop before investing in the full 12-month arc.

**The key risks** cluster into three cascades: (1) **Pedagogical** — the Aboutness Trap (organizing around topics, not learner outcomes), wrong sequencing (biases before logic), and the Domain-General Fallacy (assuming CT transfers without field-specific scaffolding) can produce a curriculum that feels comprehensive but changes no thinking behavior. (2) **Engagement** — isolation dropout is the single biggest predictor of self-guided program failure; the curriculum must simulate mentorship through author voice, peer accountability prompts, and emotional arc design. (3) **Technical** — vault rot (orphan notes, frontmatter drift, tag sprawl) silently degrades the knowledge graph over 12 months; Month 04 must include a vault-hygiene module that teaches maintenance as a meta-skill.

## Key Findings

### Recommended Stack

From STACK.md (confidence: HIGH — all plugin versions verified against GitHub releases within the last week):

This is an **Obsidian plugin stack, not a software stack.** The recommended technology is the Obsidian vault itself, extended with carefully chosen community plugins that are actively maintained and widely adopted.

**Core technologies (Tier 1 — Must-Have):**
- **Templater 2.22.1**: Dynamic template injection with date math, file metadata, frontmatter access, and user prompts. Replaces the core Templates plugin. Essential for auto-populating exercise sheets and monthly MOCs.
- **Dataview 0.5.70**: Query engine for progress dashboards, exercise-backlog views, calibration tracking tables. 9.1k stars, new maintainer actively developing.
- **Meta Bind 1.5.0**: Interactive form widgets (confidence sliders, inline selects, progress bars) that write directly to YAML frontmatter. Critical for making exercise sheets interactive.
- **Obsidian Git 2.38.3**: Automatic version control and backup via git. 11.3k stars. Provides rollback safety across 12 months of work.

**Quality-of-life (Tier 2):** Excalidraw 2.23.12 for visual concept mapping (argument diagrams, logic trees), Advanced Tables 0.23.2 for markdown table formatting.

**Conditional (Tier 3):** Charts 3.9.0 for Brier score visualization — only if needed. Last release Jan 2024 (stale — watch before installing).

**Critical anti-recommendations:** Avoid Calendar plugin (frozen since 2021), Periodic Notes (dormant 2022), Make.md / DB Folder (creates plugin lock-in), Canvas for navigation (corruptible JSON), Obsidian Publish (interactive widgets don't work on published sites). Use plain markdown + YAML frontmatter.

### Expected Features

From FEATURES.md (confidence: HIGH — verified against existing vault, Obsidian ecosystem docs, and competitor analysis):

**Must have (table stakes):**
- 12 monthly MOCs with clear structure and Dataview-powered progress — students need to know what to do each week
- Daily note templates with month-keyed prompts — extends existing Thinking Journal/
- Weekly check-in structure — forces reflection on what stuck
- Exercise templates per discipline — Templater-powered with YAML frontmatter
- Spaced repetition integration — `#flashcards` tag with Q&A and cloze card syntax
- Progress dashboard — Dataview-driven, showing completion %, forecast activity, journal streak
- Self-check quizzes with answer reveal — Obsidian callout syntax, no plugin needed
- Cross-linking to existing vault content (Biases, Fallacies, Mental Models)
- Forecast and Claim templates updated with curriculum-tracking fields
- Onboarding (Start Here note with required plugins list and setup checklist)

**Should have (differentiators — what makes this uniquely valuable for researchers):**
- **Research Audit Framework** — the capstone deliverable: a unified paper evaluation workflow combining ALL curriculum disciplines into one repeatable process
- **Belief calibration as integrated practice** — year-long confidence tracking with Brier scores, calibration curves, monthly update prompts
- **Paper-first pedagogy** — every concept applied to a real academic paper within the same week
- **Spiral curriculum (6 disciplines × 12 months)** — topics revisited at increasing depth with explicit cross-month backlinks
- **Field-agnostic template system** — critique sections work across chemistry, economics, psychology, etc.
- **Uncertainty quantification in every exercise** — mandatory confidence field and update trigger
- **Self-assessment calibration feedback loop** — predicted vs. actual quiz scores targeting Dunning-Kruger
- **Belief audit (before/after)** — students log positions on key questions in Month 1 and revisit quarterly

**Defer (v2+):**
- Full Brier score visualization across all 12 months
- Interactive Canvas-based curriculum map
- Curriculum git template (ready-to-fork vault)
- Evidence-based difficulty adjustments from pilot data
- Optional "teaching edition" for group facilitation

### Architecture Approach

From ARCHITECTURE.md (confidence: HIGH — verified against existing vault MOCs, templates, and directory layout):

The architecture is a **4-level MOC hierarchy** (Hub → Thread MOCs → Monthly MOCs → Weekly MOCs) with unidirectional linking to the existing reference library. The curriculum lives in a single top-level `Curriculum/` directory that extends the existing vault without modifying any existing notes (except adding one link on the root `Critical Thinking.md` hub).

**Major components:**
1. **Curriculum Hub** — vault entry point linking to all 12 months, 4 threads, and the Dashboard
2. **Thread MOCs (4)** — map spiral arcs across months (Logic, Probability/Bayes, Scientific Reasoning, Metacognition) — these are the backbone of the spiral design
3. **Monthly MOCs (12)** — week-by-week navigation with thread coverage, exercise checklist, reference links, and "spiral forward" pointers
4. **Weekly MOCs (48)** — daily prompts, assigned exercises, paper readings, and self-assessment links
5. **Dashboard** — Dataview-driven progress aggregation from frontmatter across all curriculum notes
6. **Reference Library (existing)** — pure reference notes that curriculum links to but never modifies

**Key patterns:**
- **MOC-as-Navigation** — every folder has an MOC; students never browse folder trees
- **Spiral Spacing** — concepts return at N+2 or N+3 month intervals with increasing depth (Foundation → Application → Synthesis → Teaching)
- **Frontmatter-as-State** — all progress data lives in YAML, queried by Dataview
- **Paper-First Pedagogy** — every week includes at least one paper critique applying concepts to real research
- **Calibration Loop** — every exercise includes confidence rating; Dashboard tracks Brier scores

**Build order dependency:** Thread MOCs → Monthly MOC → Weekly MOCs → Lesson content → Dashboard queries. Build Month 01 and Month 12 first (define start and end), then fill middle months.

### Critical Pitfalls

From PITFALLS.md (confidence: HIGH — academic sources (Willingham, van Gelder, Frontiers in Education), Obsidian community data, and curriculum design research corroborate the top findings):

**1. The Aboutness Trap (P1) — CRITICAL**
The curriculum must NOT be organized as a survey of critical thinking topics. It must be organized around learner transformations: "After this month, the student can ______." This is the single most consequential design decision. If Month 01 is "Introduction to Critical Thinking" instead of "Spot a Weak Argument," the entire curriculum will produce passive consumers of CT content, not better thinkers.

**2. Isolation Dropout (P8) — CRITICAL**
The #1 predictor of self-guided program failure (confirmed by multiple systematic reviews covering 110+ studies). Students fade quietly by Month 03. The curriculum cannot fully solve this (it's structural), but mitigation includes: author voice with personality, "Dear Researcher" letters, peer accountability prompts in templates, cohort formation suggestions, and structured peer review fields.

**3. Wrong Sequencing (P5) — CRITICAL**
Teaching biases before logic, or Bayes before probability, is the most common sequencing error and it produces superficial understanding. Correct order: Normative models (what is a good argument) → Fallacies as deviations → Probability foundations → Bayesian reasoning/statistics → Cognitive biases → Scientific reasoning/integration.

**4. The Domain-General Fallacy (P3) — CRITICAL**
CT skills don't transfer automatically across domains. Researchers need field-specific scaffolding. Every exercise must have two versions (generic for skill acquisition + field-specific with domain-bridge templates). Months 10-12 are entirely domain-integration.

**5. Vault Rot Cascade (P6 + P9 + P13) — HIGH**
Orphan notes (20-30% by Month 06), frontmatter drift (silently breaks dashboards), and tag sprawl (100+ near-duplicate tags) compound each other. Month 04 must include a dedicated vault hygiene module teaching orphan detection, frontmatter linting, and tag maintenance as meta-skills.

## Implications for Roadmap

Based on combined research findings, the following phase structure is recommended:

### Phase 0: Vault Foundation & Onboarding Setup
**Rationale:** Every other phase depends on having the right templates, plugin configuration, and folder structure in place. The onboarding experience sets the tone for the entire 12-month program and must prevent known abandonment causes before they occur.
**Delivers:**
- Pre-configured vault with Tier 1 plugins (Templater, Dataview, Meta Bind, Obsidian Git)
- `Curriculum/` directory structure with all month/week folders
- All Templater templates (Lesson Note, Exercise Sheet, Paper Critique, Weekly Review, Monthly Synthesis, Self-Assessment)
- `Start Here.md` onboarding note with setup checklist, vault tour, and philosophy ("the vault is a tool, not the project")
- Obsidian Git auto-commit configured (30-min interval)
- Root `Critical Thinking.md` hub updated with one link to Curriculum Hub
**Addresses features from FEATURES.md:** Onboarding (Start Here), Forecast/Claim template updates
**Avoids pitfalls from PITFALLS.md:** P10 (Plugin Overprovisioning — only Tier 1 installed), P19 (Sync Corruption — git-only sync policy communicated), P7 (Vault Perfectionism — orientation sets expectations), P17 (Folder Maximalism — shallow hierarchy enforced)
**Stack elements used:** Templater (all templates), Dataview (dashboard scaffold), Meta Bind (frontmatter widgets), Obsidian Git (version control)
**Research flag:** Well-documented patterns. Templates can follow existing `_templates/` conventions. No deeper research needed.

### Phase 1: Curriculum Design & Thread Architecture
**Rationale:** Pedagogical pitfalls (P1, P2, P5) are the highest-risk items and must be addressed BEFORE any content is written. The spiral curriculum's dependency on a multi-dimensional content matrix means threads and month arcs must be designed holistically. This phase defines the learning outcomes, sequencing, and structure that all other phases implement.
**Delivers:**
- Program-level outcome statement (the North Star: "By month 12, student can independently audit a research paper...")
- 12 specific monthly outcome statements using Bloom's taxonomy action verbs
- 4 Thread MOCs with month-by-month progression (Foundation → Application → Synthesis → Teaching)
- Content matrix: 12 months × 6 disciplines, showing which concepts appear when and at what depth
- `depth-level:: 1|2|3|4` frontmatter convention for spiral tracking
- Sequencing validated against: Critical Thinker Academy, UC Berkeley Sense & Sensibility & Science, van Gelder 2005
- Entry diagnostic quiz (Month 00) for self-assessment and starting-month recommendation
- Minimum viable path design (which lessons are Core vs. Enrichment)
- Emotional arc design for Months 10-12 (peak/valley/peak pacing)
**Addresses features from FEATURES.md:** Spiral curriculum design (highest dependency), Research Audit Framework (template designed early, filled later)
**Avoids pitfalls from PITFALLS.md:** P1 (Aboutness Trap — skill-building arcs, not topic surveys), P2 (Implicit Instruction — explicit named strategies), P5 (Wrong Sequencing — normative-first order), P14 (Procrustean Sequencing — entry quiz + tiered content), P16 (Final-Stretch Dropout — emotional arc designed), P18 (Belief Preservation — Month 08 slot designed)
**Research flag:** HIGH — this phase needs deeper research during planning. The sequencing validation against known curricula is critical. `/gsd-plan-phase --research-phase 1` recommended for: entry diagnostic design methodology, thread progression research from CT education literature, and emotional arc validation.

### Phase 2: Content Authoring — Months 01-03 (MVP)
**Rationale:** The MVP covers the first 3 months as a proof of the core learning loop. This is enough to validate: (a) does the spiral pattern actually work, (b) are time budgets realistic, (c) do the templates produce quality student output. Writing Month 01 and Month 12 first (defining the beginning and end) provides a framework for the middle months.
**Delivers:**
- Month 01 "Foundations" — complete: What is critical thinking, System 1/2, arguments, premises/conclusions, introduction to all 4 threads at Foundation depth
- Month 02 "Formal Tools" — complete: Validity/soundness, fallacies as deviations, probability intuition, conditional probability
- Month 03 "Probability & Bayes" — complete: Bayes theorem, calibration, informal fallacy recognition
- All associated exercise sheets (70% exercise / 30% reading ratio per P12 prevention)
- Model answers for all objective exercises
- Spaced repetition flashcards embedded in all lessons
- 1-2 exemplar paper critiques (psychology replication studies)
- Weekly review templates with orphan-detection Dataview queries
- Basic Dashboard (Dataview): exercises completed, forecast activity, journal streak
- "Dear Researcher" month-opening letters with author voice
**Addresses features from FEATURES.md:** Months 01-03 MOCs, daily note templates, weekly check-in, exercise templates (first 3 disciplines), paper critique template, spaced repetition integration, basic progress dashboard, cross-linking to vault MOCs, belief audit initial prompt
**Avoids pitfalls from PITFALLS.md:** P4 (Cognitive Overload — 3-5-3 rule enforced), P12 (Deliberate Practice Gap — exercise-to-reading ratio flipped), P15 (No Human Voice — "Dear Researcher" letters), P20 (Missing Formative Assessment — end-of-month mastery checks with model answers), P3 (Domain-General — field-specific exercise options)
**Stack elements used:** All Tier 1 plugins fully utilized
**Architecture components implemented:** Monthly MOCs, Weekly MOCs, Exercise Notes, Paper Critique notes, Self-Assessment notes, Basic Dashboard views
**Research flag:** LOW — well-documented patterns. The content itself requires domain expertise but the structural patterns (templates, exercises, model answers) are standard. Skip research-phase for Phase 2 planning.

### Phase 3: Vault Hygiene Month (Embedded in Month 04)
**Rationale:** Research shows vault rot (orphans, frontmatter drift, tag sprawl) begins silently around Month 04 when students have 50-100 notes. Teaching maintenance as a meta-skill at this point prevents the entire vault from degrading in Months 05-12. This is not a separate deliverable — it's embedded as Month 04 content.
**Delivers:**
- Month 04 "Statistics & Scientific Reasoning" curriculum content
- Vault hygiene lesson: orphan detection with Dataview, frontmatter linting, tag audit
- Controlled frontmatter vocabularies reinforced through templates
- Monthly synthesis template with graph-walk exercise ("open graph view, find under-connected clusters, add 3+ links")
- Link-before-you-leave rule embedded in all templates
- Quarterly frontmatter audit pattern established (repeated at Month 06, Month 09)
**Addresses pitfalls from PITFALLS.md:** P6 (Orphan Rot — detection taught as skill), P9 (Frontmatter Drift — linting exercise + controlled vocabularies), P13 (Tag Sprawl — tag audit exercise)
**Research flag:** LOW — standard Obsidian maintenance patterns. Vault Physician plugin docs serve as reference.

### Phase 4: Content Authoring — Months 05-09 (Deepen)
**Rationale:** With the pattern proven and vault hygiene established, this phase deepens the spiral. Threads move from Application to Synthesis. Exercises require combining multiple concepts. Paper critiques reference both reference library AND earlier curriculum concepts. This is the bulk of curriculum content.
**Delivers:**
- Months 04-06 MOCs: Statistics, Scientific Reasoning, Paper Analysis
- Months 07-09 MOCs: Metacognition, Debiasing, Causal Reasoning
- Exercise templates for Statistics and Scientific Reasoning (remaining disciplines)
- "Find a time you were wrong" exercise (Month 05)
- Adversarial collaboration exercise templates
- Month 08: "Thinking About Your Own Thinking" — dedicated metacognition + identity-protective cognition module
- Calibration dashboard (predicted vs actual quiz scores)
- Diverse-field exemplar critiques (biomedical, social science, economics)
- Pre/post-mortem templates for research studies
- Quarterly frontmatter audits (Month 06, Month 09)
- "Common sticking points" callouts added to all months based on beta feedback
**Addresses features from FEATURES.md:** Months 04-09 MOCs, remaining exercise templates, calibration dashboard, diverse-field exemplars, self-assessment calibration quizzes
**Avoids pitfalls from PITFALLS.md:** P18 (Belief Preservation — Month 08 specifically designed for this), P11 (Pile-Up — minimum viable paths maintained), P15 (No Human Voice — continued)
**Research flag:** MEDIUM — Month 08 (metacognition) is novel and may need deeper research into identity-protective cognition strategies. `/gsd-plan-phase --research-phase 8` recommended for the metacognition module design.

### Phase 5: Content Authoring — Months 10-12 (Integration & Capstone)
**Rationale:** The final stretch must feel like a culmination, not a continuation. Research on final-stretch dropout (P16) shows students stop at Month 09-10 without explicit finish-line design. The emotional arc: Month 10 peak (first complete paper audit), Month 11 valley (consolidation), Month 12 peak (final Research Audit).
**Delivers:**
- Month 10 "First Complete Paper Audit" — milestone event, messy/imperfect by design
- Month 11 "Gap-Filling & Review" — lighter pace, revisiting weak areas, optional deep dives
- Month 12 "Final Research Audit" — capstone: student audits a paper of their choice using all 12 months of skills
- Research Audit Framework final version — all 6 disciplines integrated into one reusable workflow
- Full Brier score history and calibration curve visualization
- "Certificate of Completion" markdown note (psychological endpoint)
- Belief Audit before/after comparison report
- Curriculum git template generation
**Addresses features from FEATURES.md:** Months 10-12 MOCs, Research Audit Framework (final), full Brier score visualization, belief audit comparison report, curriculum git template
**Avoids pitfalls from PITFALLS.md:** P16 (Final-Stretch Dropout — peak/valley/peak emotional arc), P18 (Belief Preservation — audit framework includes reflective self-assessment)
**Research flag:** LOW — the Research Audit Framework is well-defined in FEATURES.md and ARCHITECTURE.md. The content is synthesis of prior months, not new concepts.

### Phase 6: Beta Testing & Refinement
**Rationale:** Every pitfall source emphasizes the need for beta testing before full release (see PITFALLS.md authoring anti-patterns). Testing Months 01-03 with 3-5 researchers reveals pacing problems, confusing instructions, and structural issues before the full 12-month investment.
**Delivers:**
- Beta test of Months 01-03 with 3-5 researchers
- Time-budget validation (target: 3-5 hrs/week)
- Confusion-point collection and remediation
- Model answer quality review
- Plugin compatibility verification
- "Common sticking points" documentation
- Revised content based on beta feedback
**Avoids pitfalls from PITFALLS.md:** All authoring anti-patterns (no beta testing, average-researcher assumption, linear writing without review)
**Research flag:** N/A — this is a testing phase, not a research phase.

### Phase Ordering Rationale

- **Phase 0 first** because every content authoring phase depends on templates and folder structure being in place. Onboarding prevents 5+ pitfalls before they occur.
- **Phase 1 before Phase 2** because pedagogical decisions (sequencing, outcomes, thread architecture) are the most consequential. Changing them after content is written requires rewriting. The spiral matrix must be designed before any single month is authored.
- **Phase 2 (Months 01-03) before Phase 4 (Months 05-09)** because the MVP validates the learning loop before committing to the full content investment.
- **Phase 3 (Vault Hygiene) embedded in Month 04** because vault rot starts silently around 50+ notes. Month 04 is the natural point to intervene before the problem compounds.
- **Phase 5 (Months 10-12) last** because these months reference concepts from ALL prior months. Writing them earlier would produce weak forward references.
- **Phase 6 after all content** because beta testing without content is meaningless. But beta test Months 01-03 early (after Phase 2) while Phase 4-5 content is being written, so Month 01-03 issues are fixed before full release.

### Research Flags

Phases likely needing deeper research during planning:
- **Phase 1 (Curriculum Design):** Entry diagnostic methodology, thread progression research, sequencing validation against CT education literature. `/gsd-plan-phase --research-phase 1` recommended.
- **Phase 4, Month 08 (Metacognition):** Identity-protective cognition strategies, debiasing techniques that actually transfer. This is the least well-documented area in CT education. `/gsd-plan-phase --research-phase 8` recommended.

Phases with standard patterns (skip research-phase):
- **Phase 0 (Vault Foundation):** Well-documented Obsidian patterns. Follow STACK.md plugin configurations and template patterns.
- **Phase 2 (Content Authoring):** Exercise design, model answer authoring, lesson structure — established patterns from FEATURES.md and STACK.md.
- **Phase 5 (Integration/Capstone):** The Research Audit Framework template is well-defined in FEATURES.md. Content is synthesis of prior months.

## Confidence Assessment

| Area | Confidence | Notes |
|------|------------|-------|
| Stack | HIGH | All plugin versions verified against GitHub releases (June 2026). Existing vault `.obsidian/` config directly read. Anti-recommendations corroborated by last-release dates. |
| Features | HIGH | Feature landscape directly derived from existing vault analysis + Obsidian ecosystem documentation + competitor analysis. MVP boundaries clearly defined by dependency analysis (FEATURES.md). |
| Architecture | HIGH | Patterns verified against 6+ Obsidian vault architecture sources. Existing vault MOCs, templates, and directory layout directly read as ground truth. |
| Pitfalls | HIGH | Critical pitfalls corroborated by academic sources (Willingham 2008, van Gelder 2005, Stanford Encyclopedia of Philosophy, Frontiers in Education 2026). Technical pitfalls verified against Obsidian Forum reports, vault-health plugin data, and community best practices. |

**Overall confidence:** HIGH — all four research areas converge on a consistent, well-evidenced approach.

### Gaps to Address

- **Entry diagnostic quiz design (Phase 1):** The concept of an entry self-assessment is recommended but no validated instrument exists in this context. The quiz must be designed from scratch — this is the highest-risk unknown. Recommend borrowing from existing CT assessments (Halpern, Watson-Glaser) and adapting to the 4-thread structure. This needs deeper research during Phase 1 planning.
- **Field-specific exercise scaffolding (Phase 2):** The "domain-bridge templates" concept (P3 prevention) is sound in theory but unproven in this specific vault context. The first field-specific template needs pilot testing with a researcher from that field to validate the scaffolding approach.
- **Months 10-12 capstone design (Phase 5):** While the Research Audit Framework concept is well-defined, the specific evaluation rubric for the capstone audit has not been designed. This should include: (a) criteria for a "passing" audit, (b) model audit at different quality levels, (c) self-scoring guidelines. Design this during Phase 1 so it shapes all prior content.
- **Beta testing scope:** The plan calls for 3-5 researchers testing Months 01-03. What recruitment channel? What demographics? The curriculum is field-agnostic but the beta test needs field diversity (at minimum: one quantitative field, one qualitative field, one biomedical) to validate the domain-bridge approach.

## Sources

### Primary (HIGH confidence)
- **Dataview GitHub Releases** (0.5.70) — Version verification, active maintenance confirmation
- **Templater GitHub Releases** (2.22.1) — Version verification, API capabilities
- **Meta Bind GitHub Releases** (1.5.0) — Version verification, inline widget support
- **Obsidian Git GitHub Releases** (2.38.3) — Version verification, auto-commit patterns
- **Existing vault `.obsidian/core-plugins.json`** — Core plugin configuration ground truth
- **Existing vault templates** (`_templates/Claim.md`, `_templates/Forecast.md`) — Convention patterns verified
- **Existing vault MOCs** (`Biases/Cognitive Biases.md`, `Logical Fallacies/Logical Fallacies.md`) — MOC patterns verified
- **Willingham, D.T. (2008). Critical Thinking: Why Is It So Hard to Teach?** — CT is domain-dependent
- **van Gelder, T. (2005). Teaching Critical Thinking: Some Lessons From Cognitive Science** — Deliberate practice essential
- **Stanford Encyclopedia of Philosophy (2026). Critical Thinking: Educational Methods** — Mixed approach best evidence
- **Frontiers in Education (2026). From implicit to explicit** — Implicit instruction perpetuates inequity
- **Springer (2024). Dropout in online higher education** — Isolation as primary dropout factor (110+ studies)
- **NIH/PMC (2022). Persistence and Dropout in Higher Online Education** — Feedback insufficiency

### Secondary (MEDIUM confidence)
- **MoreBetterLabs (2026). The 2 Traps That Kill Online Courses** — Aboutness Trap, Dual Minimalism framework
- **She Talks (2026). Why Experts Build the Worst Online Courses** — Final-stretch dropout pattern
- **BrainCert (2026). Why Learners Drop Off** — Pile-up effect (36% re-engagement stat)
- **Critical Thinker Academy** — Curriculum sequencing: logic before biases
- **UC Berkeley Sense & Sensibility & Science** — Detailed topic sequencing
- **Obsidian Forum — Vault performance** — Plugin startup time, sync corruption with cloud drives
- **Vault Physician / Vault Plus plugins** — Orphan rate data (20-30% at 400+ notes)
- **Obsidian vault structure guides** — Shallow folder principle, MOC-over-folders
- **Course and Curriculum Builder (Breadcrumbs)** — Course→Module→Lesson hierarchy patterns
- **blinboyan/obsidian-pairlearn** — Dataview progress dashboards (verified repo)
- **ABO896/obsidian-university-workflow** — Template patterns (verified repo)

---

*Research completed: 2026-06-14*
*Ready for roadmap: yes*
