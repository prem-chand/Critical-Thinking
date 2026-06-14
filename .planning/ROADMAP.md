# Roadmap: Critical Thinking for Researchers — 12-Month Curriculum

## Overview

This roadmap transforms an existing Obsidian vault (with Biases, Fallacies, Mental Models, Claim Analysis, Forecasts, and Paper Reviews) into a structured 12-month self-guided curriculum that teaches researchers critical thinking through philosophy, logic, probability, statistics, scientific reasoning, and paper critique. The curriculum lives entirely within the vault as interconnected markdown notes — no code, no build steps, no external tooling.

Seven phases build from vault foundation → curriculum design → content authoring in 3-month blocks → beta testing and refinement. Each phase delivers a complete, verifiable curriculum capability. The MVP (Phases 0-2) proves the learning loop through Months 01-03 before committing to the full 12-month arc.

## Phases

- [ ] **Phase 0: Vault Foundation & Onboarding Setup** - Plugins configured, templates authored, folder structure in place, Start Here note written
- [ ] **Phase 1: Curriculum Design & Thread Architecture** - Outcomes defined, spiral matrix designed, entry quiz created, 4 Thread MOCs built
- [ ] **Phase 2: Content Authoring — Months 01-03 (MVP)** - First 3 months complete with exercises, model answers, paper critiques, and basic dashboard
- [ ] **Phase 3: Vault Hygiene & Months 04-06 Content** - Months 04-06 authored with vault hygiene module embedded in Month 04
- [ ] **Phase 4: Content Authoring — Months 07-09 (Deepen)** - Causal reasoning, metacognition, adversarial collaboration, diverse-field critiques
- [ ] **Phase 5: Content Authoring — Months 10-12 (Integration & Capstone)** - Research Audit Framework, capstone paper audit, Brier score history, certificate
- [ ] **Phase 6: Beta Testing & Refinement** - 3-5 researchers test Months 01-03, feedback remediated

## Phase Details

### Phase 0: Vault Foundation & Onboarding Setup
**Goal**: The vault is ready for curriculum authoring — plugins configured, folder structure in place, all templates authored, onboarding written, root hub linked.
**Mode**: mvp
**Depends on**: Nothing (first phase)
**Requirements**: INFRA-01, INFRA-02, INFRA-03, INFRA-04, INFRA-05, INFRA-06, VAULT-05
**Success Criteria** (what must be TRUE):
  1. A new student opening the vault for the first time can follow "Start Here.md" and have all Tier 1 plugins (Templater, Dataview, Meta Bind, Obsidian Git) working within 15 minutes
  2. `Curriculum/` directory exists with subdirectories for all 12 months and 48 weeks
  3. All 6 Templater templates (Lesson Note, Exercise Sheet, Paper Critique, Weekly Review, Monthly Synthesis, Self-Assessment) exist, auto-populate frontmatter, and include the "link-before-you-leave" rule
  4. The root "Critical Thinking.md" hub shows a direct link to the Curriculum Hub
  5. Obsidian Git auto-commits the vault every 30 minutes with no user intervention
**Plans**: TBD

### Phase 1: Curriculum Design & Thread Architecture
**Goal**: The entire 12-month curriculum is designed at the outcome and thread level — what students learn, in what order, how depth progresses, and how to start.
**Mode**: mvp
**Depends on**: Phase 0
**Requirements**: CURD-01, CURD-02, CURD-03, CURD-04, CURD-05, CURD-06, CURD-07, CURD-08, EXER-06
**Success Criteria** (what must be TRUE):
  1. A new visitor can take the entry diagnostic quiz (Month 00) and receive a starting-month recommendation based on their responses
  2. The content matrix (12 months × 6 disciplines) clearly maps which concept appears in which month at which depth level — no gaps, no orphan depth-levels
  3. All 12 monthly outcome statements use distinct Bloom's taxonomy action verbs and are progressive (foundational → applied → synthesis)
  4. The 4 Thread MOCs (Logic & Reasoning, Probability & Statistics, Scientific Reasoning, Metacognition & Calibration) show Foundation → Application → Synthesis → Teaching arcs across the 12 months
  5. The minimum viable path (Core vs Enrichment) is documented and the emotional arc for Months 10-12 is designed with peak/valley/peak pacing
  6. The Belief Audit (before/after) template exists for Month 01 logging and quarterly revisit
**Plans**: TBD

### Phase 2: Content Authoring — Months 01-03 (MVP)
**Goal**: The first 3 months of curriculum content exist end-to-end — proving the core learning loop (lesson → exercise → paper application → self-assessment → dashboard tracking) before committing to the full 12 months.
**Mode**: mvp
**Depends on**: Phase 1
**Requirements**: CONT-01, CONT-02, CONT-03, CONT-04, CONT-05, CONT-06, EXER-01, EXER-02, EXER-03, EXER-04, EXER-05, PAPR-01, PAPR-02, TRCK-01, TRCK-05
**Success Criteria** (what must be TRUE):
  1. A student can open Month 01 and follow 12 weeks of structured daily/weekly content across all 4 threads at Foundation depth — with week structure, exercises, and paper readings clearly navigable from the Monthly MOC
  2. Every exercise sheet has a model answer accessible for self-check, and all lessons embed spaced repetition flashcards using `#flashcards` tagging with Q&A
  3. The basic Dataview dashboard shows exercise completion counts, forecast activity, and journal streak
  4. The paper critique template is complete and 2-3 exemplar critiques exist for psychology replication studies
  5. "Dear Researcher" month-opening letters with author voice exist for Months 01, 02, and 03
**Plans**: TBD

### Phase 3: Vault Hygiene & Months 04-06 Content
**Goal**: Months 04-06 curriculum is complete, and the vault hygiene module embedded in Month 04 teaches students to maintain their knowledge graph — preventing orphan rot, frontmatter drift, and tag sprawl before they compound.
**Mode**: mvp
**Depends on**: Phase 2
**Requirements**: CONT-07, CONT-08, CONT-09, CONT-10, CONT-11, TRCK-02, VAULT-01, VAULT-02, VAULT-03, VAULT-04
**Success Criteria** (what must be TRUE):
  1. Month 04 content teaches statistics & scientific reasoning AND includes a vault hygiene lesson where students run a Dataview orphan-detection query, perform a frontmatter linting exercise, and complete a tag audit
  2. Month 05 deepens scientific reasoning with study design, confounds, and replication concepts
  3. Month 06 covers Paper Analysis I with structured critique and bias detection in published work
  4. The calibration dashboard shows predicted vs actual quiz scores for the student's self-assessments
  5. The monthly synthesis template includes a graph-walk exercise, and the quarterly frontmatter audit pattern is documented for reuse in Months 06 and 09
  6. Monthly MOCs (04-06) and Weekly MOCs (13-24) all exist with thread coverage and exercise checklists
**Plans**: TBD

### Phase 4: Content Authoring — Months 07-09 (Deepen)
**Goal**: The spiral deepens into synthesis-level work — causal reasoning, metacognition, adversarial collaboration, and diverse-field paper critiques that combine multiple curriculum disciplines.
**Mode**: mvp
**Depends on**: Phase 3
**Requirements**: CONT-12, CONT-13, CONT-14, CONT-15, CONT-16, EXER-07, EXER-08, PAPR-03
**Success Criteria** (what must be TRUE):
  1. Month 07 teaches causal reasoning with causal graphs, interventions, and counterfactuals — students can diagram a causal claim from a published paper
  2. Month 08's metacognition module includes identity-protective cognition, motivated reasoning, and practical debiasing exercises
  3. Month 09's Paper Analysis II includes adversarial collaboration templates and pre/post-mortem frameworks for study evaluation
  4. Diverse-field exemplar critiques exist for at least three domains: biomedical, social science, and economics
  5. A student can find and complete the "Find a time you were wrong" exercise (Month 05) and the adversarial collaboration exercise templates
  6. Monthly MOCs (07-09) and Weekly MOCs (25-36) all exist with spiral forward pointers to prior months
**Plans**: TBD

### Phase 5: Content Authoring — Months 10-12 (Integration & Capstone)
**Goal**: The final stretch integrates every discipline into a repeatable Research Audit Framework — students complete messy first audits, consolidate weak areas, and finish with a capstone paper audit that demonstrates all 12 months of skills.
**Mode**: mvp
**Depends on**: Phase 4
**Requirements**: CONT-17, CONT-18, CONT-19, CONT-20, CONT-21, PAPR-04, TRCK-03, TRCK-04
**Success Criteria** (what must be TRUE):
  1. Month 10 provides a first complete paper audit milestone — messy by design, focused on the experience of applying all 6 disciplines simultaneously
  2. Month 11 offers gap-filling content and a lighter review pace to prevent final-stretch dropout
  3. Month 12's Final Research Audit combines all 6 disciplines into one unified paper evaluation workflow that the student can reuse on any paper after the course
  4. The Brier score history and calibration curve visualization exists (Tier 3 Charts or ASCII) showing the student's calibration improvement across the year
  5. The Certificate of Completion markdown note exists as a psychological endpoint with personalized fields
  6. The Belief Audit before/after comparison report shows the student's logged positions from Month 01 versus their current positions
  7. Monthly MOCs (10-12) and Weekly MOCs (37-48) all exist
**Plans**: TBD

### Phase 6: Beta Testing & Refinement
**Goal**: Months 01-03 are tested by real researchers who validate time budgets, identify confusion points, confirm plugin compatibility, and provide structured feedback that improves the content before full release.
**Mode**: mvp
**Depends on**: Phase 2 (can run parallel to Phases 3-5)
**Requirements**: BETA-01, BETA-02, BETA-03, BETA-04, BETA-05, BETA-06
**Success Criteria** (what must be TRUE):
  1. 3-5 researchers have completed Months 01-03 and provided structured feedback per the beta protocol
  2. Actual time spent per week is measured and documented — the curriculum meets the 3-5 hour target or is adjusted
  3. All confusion points from beta testers are documented and remediated in the content
  4. Model answers are reviewed by at least one domain expert and corrected where needed
  5. All Tier 1 plugins (Templater, Dataview, Meta Bind, Obsidian Git) work correctly with the curriculum templates — any incompatibilities documented and fixed
  6. "Common sticking points" callout boxes are added to all content in Months 01-03 based on beta observations
**Plans**: TBD

## Progress

| Phase | Plans Complete | Status | Completed |
|-------|----------------|--------|-----------|
| 0. Vault Foundation & Onboarding Setup | 0/? | Not started | - |
| 1. Curriculum Design & Thread Architecture | 0/? | Not started | - |
| 2. Content Authoring — Months 01-03 (MVP) | 0/? | Not started | - |
| 3. Vault Hygiene & Months 04-06 Content | 0/? | Not started | - |
| 4. Content Authoring — Months 07-09 (Deepen) | 0/? | Not started | - |
| 5. Content Authoring — Months 10-12 (Integration & Capstone) | 0/? | Not started | - |
| 6. Beta Testing & Refinement | 0/? | Not started | - |
