# Feature Landscape

**Domain:** Self-guided 12-month critical thinking curriculum inside Obsidian for researchers
**Researched:** 2026-06-14
**Confidence:** HIGH

## Feature Landscape

### Table Stakes (Users Expect These)

Features that must exist or the curriculum fails as a self-guided learning tool. Users won't give credit for having these, but they'll abandon the vault if they're missing.

| Feature | Why Expected | Complexity | Notes |
|---------|--------------|------------|-------|
| **12 monthly MOCs with clear structure** | Students need to know what to do in which week. Without month-level Maps of Content with daily/weekly breakdowns, the vault is just a pile of notes — not a curriculum. | MEDIUM | Each Month MOC needs: core topics, learning objectives, links to daily notes, exercise checklist, checkpoint. Should use Dataview to auto-list incomplete exercises. |
| **Daily note templates with prompts** | Students need a blank-slate entry point each day. Without structured prompts keyed to the month's theme, journals devolve into unstructured diaries. | LOW | Extend existing `Thinking Journal/` with daily prompt templates via Templater. Prompts must shift each month to match the current topic. |
| **Weekly check-in structure** | Self-guided learners drift without periodic self-assessment. Weekly check-ins force reflection on what stuck and what didn't. | LOW | A weekly note template with: "What concept clicked?", "What am I confused about?", "Spaced repetition reviews done this week: __", "Forecasts to review". |
| **Exercise templates for each discipline** | Students need structured exercises (logic drills, probability calibration, paper critiques). Raw text prompts without templates produce unstructured output. | MEDIUM | Templater-powered note templates per exercise type. Each creates a new note with YAML frontmatter, structured sections, and auto-linking to the current month. |
| **Spaced repetition integration** | Core concepts must be retained across 12 months. Without SRS, students forget Month 1 content by Month 6 and the spiral curriculum doesn't work. | MEDIUM | Leverage existing [Obsidian Spaced Repetition plugin](https://github.com/st3v3nmw/obsidian-spaced-repetition) (v1.15.2, 2.4k stars). Embed flashcards in curriculum notes using `#flashcards` tag with `::` and `::: ` syntax for Q&A and cloze cards. Confidence: HIGH (well-documented plugin). |
| **Progress dashboard** | Students need to see where they are in the 12-month arc. Without it, they lose motivation and context around month 3-4. | MEDIUM | Dataview-powered dashboard note showing: current month, exercises completed (by tag `#exercise`), forecasts active, journal entry streak. Can use DataviewJS for progress bars. |
| **Self-check quizzes (answer-reveal)** | Must be able to verify understanding without external grader. Accordion-style or callout-based hidden answers. | LOW | Use Obsidian callout syntax (`> [!tip]`, `> [!warning]`) for pre-answer sections. Students reveal by clicking. No plugin needed. |
| **Cross-linking to existing vault content** | The curriculum must connect new learning to existing bias, fallacy, and mental model notes. Without links, students maintain separate mental buckets. | LOW | Every exercise and month MOC must include a "Related" section with wikilinks to existing MOCs. This is the architectural core of the vault-as-knowledge-graph. |
| **Forecast and claim templates integrated into curriculum** | The existing Forecast and Claim Analysis systems must be curriculum-aware. If students learn Bayesian updating in Month 4 but have nowhere to practice it, the skill doesn't stick. | LOW | Extend existing `_templates/Forecast.md` and `_templates/Claim.md` with curriculum tracking fields (`month::`). Dataview queries on the dashboard show forecast activity by month. |
| **Onboarding flow for Month 1** | First-time users need orientation. Without setup instructions, required plugins list, and a "what to expect" page, abandonment is high. | MEDIUM | Dedicated `Start Here.md` note covering: required plugins (Dataview, Templater, Spaced Repetition), vault tour, weekly time commitment (3-5 hrs), how exercises work, how the spiral curriculum works. Include a one-time setup checklist. |

### Differentiators (Competitive Advantage)

Features that make this curriculum uniquely valuable for researchers — not just "another critical thinking course" but one designed specifically for how scientists think and work.

| Feature | Value Proposition | Complexity | Notes |
|---------|-------------------|------------|-------|
| **Research Audit Framework** | A unified paper evaluation workflow that combines ALL curriculum disciplines into one repeatable process: formal logic (argument mapping) + statistical reasoning (methodology critique) + bias detection (confounding variables, motivation) + epistemology (what counts as evidence). This is the capstone deliverable. | HIGH | Create a reusable template that structures a paper audit into sequenced passes: (1) Claim extraction, (2) Argument reconstruction, (3) Statistical check, (4) Bias audit, (5) Uncertainty assessment, (6) Overall confidence. This is the single artifact a researcher keeps using after the curriculum ends. |
| **Belief calibration as a curriculum-integrated practice** | Scientists are terrible at expressing uncertainty. The curriculum doesn't just teach Bayesian updating — it builds a YEAR-LONG practice of explicit confidence tracking, forcing students to revisit and update every claim and forecast they made. | MEDIUM | Monthly "calibration review" prompt: "Revisit your active claims from Month X. What evidence has emerged? Update your confidence." Dashboard shows calibration curve (predicted confidence vs actual accuracy) over time using Brier scores from resolved forecasts. |
| **Paper-first pedagogy (apply-every-concept-immediately)** | Every new concept (syllogism, p-hacking, falsification, base rate neglect) is applied to a real academic paper within the same week. Researchers don't learn by abstract drill — they learn by critiquing actual published work in their own field. | MEDIUM | Each month includes 2-3 "application papers" from the `Paper Reviews/` directory. Exercises reference specific papers. The curriculum provides exemplar critiques; students produce their own. This is more work to build than generic exercises (need curated paper list + annotated critiques). |
| **Spiral curriculum across 12 months (not linear)** | Unlike a textbook that teaches each subject once, topics recur at increasing depth. Students encounter Bayes in Month 1 (intuition), Month 4 (calculation), Month 7 (Bayesian epistemology), and Month 10 (meta-analysis). This produces durable understanding. | HIGH | The entire curriculum must be designed as a matrix: 12 rows (months) x 6 columns (disciplines). Each cell is a revisit of the discipline at higher depth. Requires careful sequencing so later months can reference earlier content. Corollary: every note must have a `depth-level:: 1|2|3` frontmatter field. |
| **Field-agnostic template system** | A chemistry postdoc and an economics PhD use the same curriculum but apply concepts to different papers. The template system lets them plug in their own papers without the curriculum needing domain-specific content. | MEDIUM | Paper critique templates use generic sections ("Methods", "Evidence quality", "Statistical approach") that work across fields. The curriculum provides exemplar critiques from multiple disciplines (psychology replication crisis, biomedical RCTs, econ natural experiments) so every student finds a relatable model. |
| **Uncertainty quantification practice built into every exercise** | Not just "identify the fallacy" but "how confident are you that this is a fallacy? What would change your mind?" This trains the meta-cognitive muscle that separates good researchers from great ones. | LOW | Every exercise template includes a mandatory confidence field (`confidence::`) and an update trigger field (`would-update::`). The dashboard aggregates these to show calibration trends. This is cheap to add (just a frontmatter field) but transforms the learning quality. |
| **Self-assessment calibration feedback loop** | Students often overestimate their understanding. Monthly "calibration quizzes" ask them to predict their score before taking the quiz, then compare predicted vs actual. This targets the Dunning-Kruger effect head-on. | LOW | A DataviewJS block that shows: "Last month you predicted X% but scored Y%. Your calibration error is Z%." Paired with a reflection prompt. No external data needed — everything is in the YAML frontmatter. |
| **Curriculum-before-and-after belief audit** | Students log their positions on 5-10 key questions (e.g., "How confident are you that most published research findings are true?") in Month 1 and revisit them each quarter. This measures the curriculum's actual impact on their thinking. | MEDIUM | A living note (`Belief Audit.md`) with initial confidence ratings and quarterly re-assessments. Uses inline Dataview fields. Creates an automatic chart of belief shifts over the year. Powerful for testimonials and personal motivation. |

### Anti-Features (Commonly Requested, Often Problematic)

Features that seem valuable but would actively harm the curriculum, inflate scope, or violate the Obsidian-only constraint.

| Anti-Feature | Why Requested | Why Problematic | Alternative |
|---|---|---|---|
| **Custom Obsidian plugins** | "We need exactly the right interface" | Building and maintaining custom plugins across Obsidian versions is a full-time job. Every plugin update risks breaking the curriculum. The curriculum's value is CONTENT, not code. The existing plugin ecosystem (Dataview, Templater, Spaced Repetition) covers everything needed. | Use community plugins. Design around their capabilities. If a feature isn't possible with them, reconsider the feature. |
| **Video or narrated content** | "Researchers learn from lectures" | Video is out of scope per PROJECT.md. It bloats the vault (can't store in git), dates quickly, and contradicts the text-first, Obsidian-native design. More importantly, video is passive — the curriculum is designed for ACTIVE learning through writing and exercises. | Text explanations with worked examples. Link to external lecture videos if students want them, but don't bundle them. |
| **Automated grading of exercises** | "How will students know if they're right?" | Impossible without an answer key for every possible response to open-ended critical thinking exercises. Attempting automated grading leads to multiple-choice-only exercises (which don't teach critical thinking) or brittle AI evaluation that gives false feedback. | Self-check answer reveals for objective exercises (logic drills, probability calculations). For subjective exercises (paper critiques, argument analysis), provide exemplar critiques at known quality levels with explanatory commentary. |
| **Social features / discussion forums** | "Students need peer discussion" | Requires a web app, user accounts, moderation, and ongoing maintenance — completely outside the Obsidian-only constraint. Also, the curriculum is designed for independent self-study by busy researchers who can't coordinate schedules. | The curriculum can suggest forming a "critical thinking reading group" at the student's institution, but this is an optional enhancement, not a built-in feature. Document how to do it. |
| **External web app or database** | "We need centralized progress tracking" | Breaks Obsidian-only constraint. Requires hosting, authentication, data privacy compliance (especially for research institutions). Costs money and attention to maintain. | Everything lives in the vault. Sync via git, Obsidian Sync, or cloud folder. Dashboard is generated from local data. |
| **Real-time tutoring or Q&A** | "Students will get stuck" | Requires staffing, expertise, and availability. Not feasible for a self-guided curriculum without ongoing funding. Also, struggling productively is part of critical thinking — premature answers short-circuit learning. | Build an extensive FAQ/glossary. Include worked examples for every exercise type. Provide "common sticking points" callouts in each month's notes based on pilot testing. |
| **Field-specific statistical modules** | "I need stats for my field specifically" | Out of scope per PROJECT.md. Creating domain-specific modules (bioinformatics, econometrics, psychometrics) for every research field would multiply the content scope by 10x and still miss fields. | Teach general statistical reasoning principles (p-value misinterpretation, effect sizes, Bayesian vs frequentist, multiple comparisons) with examples from multiple fields. The critique templates work universally. |
| **Gamification (badges, levels, leaderboards)** | "It keeps students motivated" | Researchers are intrinsically motivated by getting better at their craft — extrinsic gamification undermines this and feels patronizing. Leaderboards add privacy concerns and encourage gaming the system. | Progress dashboard shows personal trajectory, not comparison. The motivation comes from seeing one's own calibration improve over the year. If needed, add printable "completion certificate" at the end. |
| **Prerequisite screening or placement test** | "Students come in with different levels" | Creating and validating a placement test for critical thinking is a psychometric project in itself. The spiral curriculum is designed to accommodate different starting levels — everyone starts from foundational concepts and spirals up. | Month 1 is explicitly designed for beginners. Students already familiar with the content can accelerate by completing exercises faster and diving deeper into the application papers. Include "If you already know this" skip-notes at the start of each month. |

## Feature Dependencies

```
Monthly MOCs
    └──requires──> Daily note templates
    └──requires──> Exercise templates (per discipline)
    └──requires──> Spaced repetition flashcard integration
    └──requires──> Cross-linking to existing vault MOCs

Progress dashboard
    └──requires──> Dataview plugin
    └──requires──> Consistent YAML frontmatter across all notes
                        └──requires──> Template system (Templater plugin)
                        └──requires──> Frontmatter conventions documented

Research Audit Framework
    └──requires──> Exercise templates for ALL 6 disciplines
    └──requires──> Paper critique template
    └──requires──> Cross-linking to biases, fallacies, mental models
    └──requires──> 12 months of curriculum content (built progressively)

Calibration tracking (Brier scores)
    └──requires──> Forecast template with resolution tracking
    └──requires──> Dashboard Dataview queries
    └──requires──> Monthly calibration reviews

Spiral curriculum design
    └──requires──> Content matrix (Months × Disciplines)
    └──requires──> `depth-level::` frontmatter convention
    └──requires──> Cross-month backlinks

Self-assessment calibration quizzes
    └──requires──> Quiz template with predicted-score field
    └──requires──> Dashboard aggregation DataviewJS

Belief Audit
    └──requires──> Initial Month 1 setup
    └──enhances──> Monthly MOCs (quarterly check-in prompts)

Onboarding (Start Here)
    └──requires──> Month 01 MOC
    └──requires──> Required plugins list documented

Paper-first pedagogy
    └──requires──> Curated exemplar papers list
    └──requires──> Annotated model critiques in Paper Reviews/
    └──requires──> Generic paper critique template
```

### Dependency Notes

- **Monthly MOCs are the spine**: They require exercise templates and daily note templates to be designed *first*, because the MOC references them. Build templates before MOCs.
- **Dashboard depends on consistent frontmatter**: If notes don't have uniform YAML fields, Dataview queries return wrong/incomplete data. This means the template system must enforce consistency. Any ad-hoc note creation breaks the dashboard.
- **Research Audit Framework is a late-stage dependency**: It requires ALL 6 disciplines to have been taught, so it can't be built until Month 10-12 content exists. But the template should be designed early and filled in progressively.
- **Spiral curriculum design is the most complex dependency**: It requires a multi-dimensional content plan completed BEFORE any single month is written in full. Writing Month 1 without knowing what Month 7 covers leads to shallow forward references.
- **Calibration feedback loop depends on time**: Brier scores and calibration graphs only become meaningful after 3+ months of data. The dashboard should show "insufficient data" messages early on.

## MVP Definition

### Launch With (v1)

The minimum viable curriculum — everything needed for a student to begin Month 1 and stay engaged through Month 3. This validates the core learning loop before building the full 12 months.

- [x] Month 01 MOC with daily/weekly structure — "Foundations: What Does It Mean to Think Critically?"
  - Introduces the vault layout, Onboarding, and the 6 disciplines at depth level 1
- [ ] Month 02 MOC — "Formal Logic: Validity, Soundness, and Argument Reconstruction"
- [ ] Month 03 MOC — "Probability: Intuition, Bayes, and Calibration"
- [ ] Daily note template with month-keyed prompts
- [ ] Weekly check-in template
- [ ] Exercise templates for Philosophy, Logic, and Probability (first 3 disciplines)
- [ ] Paper critique template (generic, works across fields)
- [ ] Start Here onboarding note with required plugins and setup checklist
- [ ] Spaced repetition flashcards embedded in Months 1-3 content (core definitions and drills)
- [ ] Basic progress dashboard (Dataview): exercises completed, journal entries, forecast activity
- [ ] Forecast and Claim templates updated with `month::` and curriculum-linking fields
- [ ] Cross-linking to existing Biases, Fallacies, and Mental Models MOCs
- [ ] 1-2 exemplar paper critiques in Paper Reviews/ from a non-domain-specific field (psychology replication study)
- [ ] Belief Audit initial prompt for Month 1

### Add After Validation (v1.x)

Once Months 1-3 are tested and feedback gathered:

- [ ] Months 04-06 MOCs — Statistics, Scientific Reasoning, and Paper Analysis
  - Essential for the second half of the year; spiral references back to Months 1-3 content
- [ ] Exercise templates for Statistics and Scientific Reasoning (remaining disciplines)
- [ ] Calibration dashboard (predicted vs actual quiz scores)
- [ ] Curriculum-level progress dashboard (12-month heatmap view)
- [ ] Research Audit Framework template draft — populated with Month 1-6 content
- [ ] Additional exemplar critiques from diverse fields (biomedical, social science, economics)
- [ ] "Common sticking points" callouts added to Months 1-3 based on pilot feedback
- [ ] Spaced repetition review cadence optimization (adjust intervals based on difficulty data)

### Future Consideration (v2+)

After full 12-month content is built and validated:

- [ ] Months 07-12 MOCs — Advanced topics, synthesis, and the Research Audit capstone
- [ ] Research Audit Framework final version with all 6 disciplines integrated
- [ ] Full Brier score history and calibration curve visualization across all 12 months
- [ ] Interactive canvas-based curriculum map (Obsidian Canvas showing the full learning arc)
- [ ] Belief Audit before/after comparison report (automated from frontmatter data)
- [ ] Curriculum git template (ready-to-fork vault with blank exercise sections)
- [ ] Evidence-based difficulty adjustments: which exercises cause stalling, which are too easy
- [ ] Optional "teaching edition" with instructor notes for group facilitation at universities

## Feature Prioritization Matrix

| Feature | User Value | Implementation Cost | Priority |
|---------|------------|---------------------|----------|
| Month 01-03 MOCs | HIGH | HIGH (content creation) | P1 |
| Daily note templates | HIGH | LOW | P1 |
| Weekly check-in template | HIGH | LOW | P1 |
| Exercise templates (first 3 disciplines) | HIGH | MEDIUM | P1 |
| Paper critique template | HIGH | LOW | P1 |
| Spaced repetition integration | HIGH | MEDIUM | P1 |
| Basic progress dashboard | MEDIUM | MEDIUM | P1 |
| Start Here onboarding | HIGH | LOW | P1 |
| Forecast/Claim template updates | MEDIUM | LOW | P1 |
| Cross-linking to vault MOCs | HIGH | LOW | P1 |
| Belief Audit | MEDIUM | LOW | P1 |
| Self-assessment calibration quizzes | HIGH | LOW | P2 |
| Calibration dashboard | MEDIUM | MEDIUM | P2 |
| Months 04-06 MOCs | HIGH | HIGH | P2 |
| Exercise templates (stats, scientific reasoning) | HIGH | MEDIUM | P2 |
| Research Audit Framework template | HIGH | HIGH | P2 (design early, fill later) |
| Diverse-field exemplar critiques | MEDIUM | MEDIUM | P2 |
| Spiral depth-level matrix design | HIGH | HIGH | P1 (must be designed before content) |
| Months 07-12 MOCs | HIGH | HIGH | P3 |
| Full Brier score visualization | MEDIUM | MEDIUM | P3 |
| Interactive canvas curriculum map | LOW | MEDIUM | P3 |
| Curriculum git template | MEDIUM | MEDIUM | P3 |
| "Common sticking points" callouts | MEDIUM | LOW | P2 (after pilot) |
| Curriculum-before-and-after belief audit report | MEDIUM | LOW | P3 |

**Priority key:**
- **P1**: Must exist before first student opens the vault
- **P2**: Should add before the full 12 months are released
- **P3**: Future consideration, validate core first

## What Competitors Do vs What We Do

There is no direct competitor — no existing Obsidian vault that delivers a complete 12-month critical thinking curriculum. But there are partial analogs worth noting:

| Feature | Foundation for Critical Thinking (criticalthinking.org) | Coursera Critical Thinking courses | Our Approach |
|---------|-------------------------------------------------------|------------------------------------|--------------|
| **Format** | Paid online courses with video + quizzes | Video lectures + discussion forums + peer grading | Obsidian-only, text-first, entirely self-guided |
| **Progress** | LMS-based completion tracking | Platform-level progress | Local Dataview dashboard — no server needed |
| **Exercises** | Multiple choice + short answer (graded) | Peer-graded writing assignments | Self-check with exemplars (no grading infrastructure) |
| **Spaced repetition** | None | None | Integrated via Obsidian Spaced Repetition plugin |
| **Spiral curriculum** | Sequential modules (linear) | Sequential courses (linear) | 6 disciplines revisited monthly at increasing depth |
| **Paper application** | Optional supplementary readings | Sometimes included as readings | Mandatory — every concept applied to a real paper same week |
| **Calibration training** | Not emphasized | Not emphasized | Core feature — forecasts, claims, Brier scores, self-assessment |
| **Cost** | $$$ per course ($300-500) | $49-79/course or subscription | Free (existing vault) — student only needs Obsidian |
| **Community** | Forums, cohorts | Discussion forums | Consciously absent — designed for solo use |
| **LMS dependency** | Proprietary LMS | Coursera platform | Zero external dependencies |

## Sources

- **Obsidian ecosystem**: Official Obsidian Spaced Repetition plugin docs (stephenmwangi.com/obsidian-spaced-repetition) — HIGH confidence. Dataview plugin docs (blacksmithgu.github.io/obsidian-databview) — HIGH confidence. Templater plugin — HIGH confidence.
- **Existing vault analysis**: DIRECT reading of `/Biases/`, `/Mental Models/`, `/Claim Analysis/`, `/Forecasts/`, `/Paper Reviews/`, `_templates/` — HIGH confidence.
- **Obsidian curriculum patterns**: Forums show researchers use Obsidian for academic workflows, paper reviews, literature notes (Science Research Vault — 5.6k views, Obsidian University Workflow). No existing full curriculum vault found. MEDIUM confidence on absence.
- **Critical thinking pedagogy**: Foundation for Critical Thinking (criticalthinking.org) — 12-week programs exist but are paid and LMS-dependent. Spiral curriculum theory (Jerome Bruner) — foundational. MEDIUM confidence on curriculum design patterns.
- **Competitor analysis**: criticalthinking.org, Coursera critical thinking courses, edX philosophy/logic courses — MEDIUM confidence (public information only).
- **Spaced repetition efficacy research**: SM-2 and FSRS algorithms well-documented. Obsidian Spaced Repetition plugin uses both. — HIGH confidence.

---

*Feature research for: Self-guided 12-month critical thinking curriculum in Obsidian for researchers*
*Researched: 2026-06-14*
