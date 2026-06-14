# Domain Pitfalls

**Domain:** Self-guided Obsidian-based critical thinking curriculum for researchers
**Researched:** 2026-06-14
**Overall confidence:** HIGH — most findings corroborated across multiple sources (Stanford Encyclopedia of Philosophy, Willingham 2008/2019, van Gelder 2005, Obsidian Forum, GitHub vault-health plugins, Frontiers in Education 2026, multiple MOOC dropout systematic reviews)

---

## Quick Reference: Pitfall Severity

| # | Pitfall | Domain | Severity | Phase to Address |
|---|---------|--------|----------|------------------|
| P1 | **Aboutness Trap** — curriculum organized around topics, not learner outcomes | Pedagogical | CRITICAL | Phase 1 (Curriculum Design) |
| P2 | **Implicit Instruction Fallacy** — teaching CT as osmosis from doing research | Pedagogical | CRITICAL | Phase 1 (Curriculum Design) |
| P3 | **Domain-General Fallacy** — assuming CT skills transfer without domain practice | Pedagogical | CRITICAL | Phase 1 (Curriculum Design) |
| P4 | **Overdosing / Cognitive Load** — cramming too much per month/module | Pedagogical | CRITICAL | Phase 2 (Content Authoring) |
| P5 | **Wrong Sequencing** — teaching fallacies before argument basics / stats before probability | Domain | CRITICAL | Phase 1 (Curriculum Design) |
| P6 | **Orphan Rot** — notes without links become invisible over 12 months | Technical | HIGH | Phase 3 (Vault Hygiene) |
| P7 | **Vault Perfectionism** — building the perfect system instead of writing notes | Organizational | HIGH | Phase 0 (Onboarding) |
| P8 | **Isolation Dropout** — no feedback, peer interaction, or accountability | Engagement | CRITICAL | Phase 0 (Onboarding) |
| P9 | **Frontmatter Drift** — inconsistent metadata silently breaks dashboards | Technical | MEDIUM | Phase 3 (Vault Hygiene) |
| P10 | **Plugin Overprovisioning** — installing tools before having the problem | Technical | MEDIUM | Phase 0 (Onboarding) |
| P11 | **Pile-Up Effect** — falling behind creates self-reinforcing disengagement | Engagement | HIGH | Phase 2 (Content Authoring) |
| P12 | **Deliberate Practice Gap** — passive reading without skills practice | Pedagogical | HIGH | Phase 1 (Curriculum Design) |
| P13 | **Tag Sprawl / Inconsistency** — tags proliferate without standards | Organizational | MEDIUM | Phase 3 (Vault Hygiene) |
| P14 | **Proctrustean Sequencing** — forcing a fixed order when learners need paths | Pedagogical | MEDIUM | Phase 1 (Curriculum Design) |
| P15 | **Black Screen of Isolation** — no human voice in self-guided content | Engagement | HIGH | Phase 2 (Content Authoring) |
| P16 | **Final-Stretch Dropout** — no climax or momentum in months 10-12 | Engagement | HIGH | Phase 2 (Content Authoring) |
| P17 | **Folder Maximalism** — nested hierarchies that become burial grounds | Organizational | HIGH | Phase 0 (Onboarding) |
| P18 | **Belief Preservation Blind Spot** — curriculum doesn't address students' resistance to evidence | Domain | CRITICAL | Phase 1 (Curriculum Design) |
| P19 | **Syncing on Network Drives** — iCloud/Dropbox corruption over 12 months | Technical | CRITICAL | Phase 0 (Onboarding) |
| P20 | **Missing Formative Assessment** — no checkpoints until exercises, feedback too late | Pedagogical | HIGH | Phase 2 (Content Authoring) |

---

## Critical Pitfalls (Will Cause Rewrite or Abandonment)

### P1: The Aboutness Trap — Teaching "About" Critical Thinking Instead of Building Thinkers

**What goes wrong:** The curriculum is organized as a survey of the critical thinking *field* rather than a sequence of *learner transformations*. Month headings read like a textbook table of contents: "Introduction to Philosophy," "Formal Logic," "Probability Theory," "Cognitive Biases." Students consume information about each topic but never develop the integrated reasoning skill.

**Why it happens:** This is the default mode of experts designing curricula. The expert knows the subject's structure (philosophy → logic → probability → statistics → scientific reasoning) and reproduces that structure as the curriculum. It feels comprehensive and logical. But it's organized around the discipline, not around the learner's journey from naive to skilled reasoner.

**Consequences:**
- Students say "this was really interesting" but don't change their behavior
- Learners feel overwhelmed by theory before they've practiced any skill
- No clear through-line connecting the topics into an integrated reasoning ability
- By month 6, students can define Bayesian updating but can't apply it to a paper in their field

**Prevention:** Use the Dual Minimalism framework from MoreBetterLabs:
1. Define a **specific, measurable outcome** for the entire 12-month program (e.g., "By month 12, student can independently audit a research paper in their field for reasoning quality, identify its weakest inference, and articulate a Bayesian belief update with a Brier score.")
2. For each month, define: "After this month, the student will be able to [specific action]."
3. **Cut ruthlessly.** Every lesson earns its place by directly enabling that action. If a topic (e.g., "The History of Logical Positivism") doesn't map to a concrete skill in the paper audit, it gets cut.
4. Organize months as **skill-building arcs**, not topic surveys. Month 01 is not "What is Critical Thinking" — it's "Spot a Weak Argument."

**Detection:** The curriculum outline reads like a university course catalog. You can't state each month's outcome in a single sentence that starts with "After this month, the student can ______."

**Phase to address:** Phase 1 (Curriculum Design) — before any content is written. Fixing this after authoring means rewriting everything.

---

### P2: The Implicit Instruction Fallacy — Assuming CT Skills Develop Through Osmosis

**What goes wrong:** The curriculum assumes that if students just *do* research (read papers, write critiques, analyze claims), they'll naturally become better critical thinkers. CT skills are treated as a byproduct of domain engagement rather than as explicit, teachable cognitive strategies.

**Why it happens:** This is the dominant pedagogy in graduate education. The unstated message is: "Read enough papers and do enough research, and critical thinking will rub off on you." It's also the default of the existing vault, which provides reference notes on biases/fallacies but doesn't scaffold practice.

**Consequences:**
- Students memorize definitions of 40 biases but can't spot them in real papers
- Learners can articulate *that* they should consider alternative hypotheses but don't know *how*
- The replication crisis literature is consumed as interesting trivia, not as a tool for changing practice
- Widens equity gaps — students who enter with stronger analytical foundations improve faster; others fall further behind

**Prevention (based on Willingham 2008, van Gelder 2005, Frontiers in Education 2026):**
1. **Explicit naming and labeling.** Every cognitive strategy taught in the curriculum must be given a name, explained with 2+ examples, and labeled as a reusable strategy. Don't just practice "looking at both sides" — teach "**Adversarial Collaboration**: The strategy of constructing the strongest possible version of the argument you disagree with before evaluating it."
2. **Explicit metacognitive prompts.** Every lesson should include: "Which strategy from last month could you deploy here?" and "Before reading the next paragraph, pause and ask yourself: what do I expect to find?"
3. **Separate CT practice from domain work.** Students need dedicated exercises whose *main purpose* is to improve CT skills, not just to understand a paper. These exercises must be clearly distinct from "write a paper critique for your lab meeting."
4. **Sequenced, cumulative practice.** Skills from Month 01 are explicitly cued and required in Month 06. The spiral curriculum architecture in the STACK.md is the right approach, but only if the spirals are *explicit* ("Remember in Month 02 when we practiced identifying hidden premises? Today we'll do that for statistical arguments.")

**Detection:** Month 01 learning objectives read as "Understand X" rather than "Identify X / Apply Y / Evaluate Z." Exercise sheets are all variations of "think critically about this paper" without teaching sub-skills first. Review: Does Month 01 teach any skill that Month 06 *requires* the student to have mastered?

**Phase to address:** Phase 1 (Curriculum Design) — learning objectives must use Bloom's taxonomy action verbs (identify, apply, analyze, evaluate), not "understand."

---

### P3: The Domain-General Fallacy — Assuming CT Skills Transfer Automatically

**What goes wrong:** The curriculum teaches critical thinking skills using generic examples (syllogisms about Socrates, probability puzzles about dice, bias examples about consumer behavior) and assumes students will naturally transfer them to evaluating research papers in their own field.

**Why it happens:** This is the central finding of 40+ years of cognitive science on critical thinking (Willingham 2008, van Gelder 2005 — both HIGH confidence, verified against original publications). The brain does not treat "critical thinking" as a general skill like riding a bicycle. The processes of thinking are intertwined with the content of thought. Domain knowledge is a prerequisite, not an enhancement.

**Consequences:**
- A biology PhD student who can ace logic puzzles about Socrates may fail to detect a flawed inference in a phylogenetics paper
- The "apply to your field" sections in every lesson are skipped because the student doesn't know *how* to map the generic exercise to their domain
- Students feel like they understand the material but can't demonstrate it in context (leading to frustration and dropout — see P8)
- The curriculum is rated "interesting but not useful" by researchers who need applied skills

**Prevention:**
1. **Every exercise has two versions:** a generic version for skill acquisition (low cognitive load, focus on the strategy) and an "apply to your field" version that includes scaffolding how to map concepts. The mapping step is taught explicitly, not assumed.
2. **Domain-bridge templates:** Paper Critique Worksheets include explicit prompts like "The equivalent of 'hidden premise' in your field is a [field-specific concept] — look for assumptions about [field-specific construct]."
3. **Months 10-12 are entirely domain-integration.** By then, students have practiced enough with generic exercises that they can identify which strategy applies, but the curriculum still provides field-specific examples *across* multiple domains (experimental psychology, clinical trials, computational modeling, field ecology, etc.) so students see how the same CT principle manifests differently.
4. **If the audience spans fields (likely for researchers),** include field-tagged examples. A Dataview query can surface field-relevant examples. A student in ecology sees ecological examples; a student in neuroscience sees neuro examples.

**Detection:** Student feedback: "I understand the concepts but can't tell if my own paper review is any good." Exercise performance: Students score 90% on generic logic puzzles but 40% on applying the same logic to their field's papers.

**Phase to address:** Phase 1 (Curriculum Design) for the scaffold strategy; Phase 2 (Content Authoring) for writing dual-exercise sheets; Phases 10-12 for integration.

---

### P4: Overdosing — Cognitive Load from Cramming

**What goes wrong:** Each month packs 8-12 lessons covering too many concepts. The "Apply It" sections require reading an entire paper on top of the lesson content. Students work through 2-3 lessons in week one, hit a dense probability lesson in week two, and never recover.

**Why it happens:** The Curse of Knowledge — the expert author knows how all the pieces fit together and underestimates how much cognitive work each individual concept requires. The "Aboutness Trap" (P1) also drives this: if the month is "about" a topic, you need to cover all of it.

**Consequences:**
- Working memory overload triggers disengagement (brain's "this is too hard" response)
- Students skip the Apply It sections because they take too long, which defeats the entire paper-first pedagogy
- The pile-up effect (P11): falling behind in week 2 makes week 3 feel impossible, and the student drops out
- Low completion rates by month 3-4

**Prevention:**
1. **The 3-5-3 rule:** Each month has exactly 3 core lessons, 5 application exercises, and 3 review/reflection activities. Anything beyond this must be explicitly labeled "optional enrichment."
2. **One-screen-one-point:** Every lesson note should be summarizable in one sentence. If it can't, split it into two lessons. (From SheTalks — "One key point in around 500 words.")
3. **Applied paper reading is a separate activity from lesson reading.** The lesson should require 15 minutes of reading. The paper application is a 45-minute separate session. Do NOT combine them in one note.
4. **Time budget: 3-5 hours/week total.** If a month's content would take 8 hours to complete, cut half. The existing constraint in PROJECT.md is correct — enforce it during authoring, not at the end.
5. **Prerequisite chains must be explicit.** If Month 04 assumes knowledge from Month 02, say so. Students who start mid-year need a "what you need before this month" note.

**Detection:** A beta tester takes 8 hours to complete Month 01 instead of the budgeted 4. Lessons that open with 30+ minutes of reading before any activity.

**Phase to address:** Phase 2 (Content Authoring) — enforce time budgets per lesson during writing. Phase 3 (Beta Testing) — measure actual completion time vs. budget.

---

### P5: Wrong Sequencing — Teaching Content in the Wrong Order

**What goes wrong:** The curriculum teaches fallacies before argument basics, Bayesian reasoning before probability fundamentals, p-values before students understand sampling distributions, or (most commonly) cognitive biases before students understand what rational reasoning looks like.

**Why it happens:** Common sequencing mistakes are well-documented in CT education research and existing curricula (see Sources). The most prevalent error: starting with cognitive biases because they're "fun" and intuitive, rather than starting with normative models of reasoning. Students learn that "humans are irrational" without first learning what rationality looks like.

**Consequences:**
- Students learn bias names as labels ("oh, that's confirmation bias!") without understanding the normative model that makes it a bias
- Bayesian updating is taught as "multiply priors by likelihoods" without the conceptual foundation of what a prior even means
- Fallacy spotting becomes a parlor game — students find fallacies everywhere but can't construct valid arguments themselves
- By Month 12, the Research Audit framework is assembled but feels arbitrary because the underlying logic chain was never built

**Prevention (based on Critical Thinker Academy, LogicCheck, UC Berkeley Sense & Sensibility & Science, and HKUST syllabi):**
1. **FIRST: Normative models of reasoning.** Month 01-02 should teach: What is a good argument? (premises, conclusions, validity, soundness). Deduction vs. induction. What it means to reason correctly.
2. **SECOND: Informal fallacies as deviations from good reasoning.** You can only recognize a fallacy because you know what correct reasoning looks like. Fallacies without normative models produce bias-spotting without correction.
3. **THIRD: Probability foundations.** Before Bayes, before p-values, before calibration training: what is probability? Frequency vs. credence interpretations. Basic probability calculus. Conditional probability.
4. **FOURTH: Bayesian reasoning and statistics.** Calibration, Bayes theorem, sampling, uncertainty quantification.
5. **FIFTH: Cognitive biases.** Now that students understand normative probability and decision theory, they can see where humans deviate. This is the order Kahneman used: System 1/2, then heuristics and biases, then debiasing.
6. **SIXTH: Scientific reasoning and integration.** Falsification, paradigm shifts, replication crisis as case study, Research Audit.

**The wrong order** (most common failure): Biases → Fallacies → Logic → Probability → Stats → Science. This is the order that feels "accessible" but produces superficial understanding.

**Detection:** Month 03 has "Confirmation Bias" but Month 01 did not teach "What makes a hypothesis test valid." The Research Audit in Month 12 asks students to evaluate evidence quality but they never learned the difference between evidence strength and evidence relevance (probability foundation required).

**Phase to address:** Phase 1 (Curriculum Design) — sequencing decisions are the most consequential design choice. Change later requires restructuring all dependencies.

---

### P6: Orphan Rot — Notes Without Links Become Invisible

**What goes wrong:** Over 12 months, students create hundreds of notes (lesson notes, exercise responses, paper critiques, journal entries). Many of these notes accumulate with zero backlinks. They exist in the file system but are invisible to the graph view, invisible to navigation, and functionally lost. The knowledge graph, sold as the curriculum's core value, becomes a sparse collection of disconnected nodes.

**Why it happens:** Obsidian's linking is opt-in. Nothing in the default workflow forces a student to link their exercise response to the relevant lesson. The daily journal is a flat list of dates. Paper critiques pile up in a folder without cross-linking to biases, fallacies, or mental models. The graph view, initially exciting, becomes discouraging when 60% of notes are isolated dots.

**Consequences (verified by multiple vault-health plugins — Vault Physician, Vault Plus, Atropos — and Obsidian Forum reports):**
- After 6 months, a typical vault has 20-30% orphan notes
- Students lose confidence in the vault as a thinking tool
- Knowledge fragments — insights from Month 03 are written in an orphan note that Month 09 never sees
- The core value proposition ("a web of interlinked notes") degrades silently
- Graph view becomes a source of shame rather than motivation

**Prevention:**
1. **Template-enforced linking scaffolding.** Every exercise template MUST include a "Related Lessons" section that the student is prompted to fill with wikilinks. The template includes a placeholder comment: `%% Link to at least 2 prior lessons %%`
2. **Weekly review template includes an orphan check.** The week review template (see STACK.md) already has a Dataview query for completed exercises. Add: ````dataview TABLE WITHOUT ID file.link, tags FROM "" WHERE file.outlinks = 0 AND file.ctime > date(today) - dur(7 days) ```` Orphans created this week.
3. **Monthly synthesis includes a graph-walk exercise.** "Open the graph view. Identify one cluster that is under-connected. Create at least 3 new links between notes in that cluster."
4. **Month 04 includes a Vault Hygiene lesson.** Teach students to use Dataview to find orphans, to notice link gaps, and to do a 15-minute weekly link-maintenance session. This is a meta-skill that pays for itself in months 5-12.
5. **Link-before-you-leave rule.** Every time a student finishes a session, they must add one link from their new note to an existing note. This should be a template footer prompt.

**Detection:** After Month 03, a Dataview check shows >20% orphan rate among student-generated notes. Graph view shows a main cluster surrounded by disconnected dots.

**Phase to address:** Phase 0 (Templates) — enforce linking in template design. Phase 2 (Content Authoring) — include linking prompts in lesson text. Phase 3 (Vault Hygiene Month 04) — teach orphan awareness.

---

### P7: Vault Perfectionism — System-Building Displaces Learning

**What goes wrong:** Students spend more time organizing the vault (renaming files, adjusting folder structures, designing their "perfect system") than actually doing the curriculum. The tool becomes the project; learning critical thinking becomes secondary.

**Why it happens:** Obsidian attracts system-builders. The power of Dataview, Templater, tags, and properties makes vault-optimization feel productive. It *is* productive for knowledge management, but it's a time sink relative to the curriculum's goals. The curriculum, by providing templates and structure, paradoxically makes this *worse* if students feel the provided structure isn't "theirs."

**Consequences:**
- Students spend 2+ hours/week reorganizing instead of learning
- Frontmatter grows ever more elaborate as students add custom fields they "might query later"
- By Month 06, the vault is beautifully organized and the student is still on Month 03 content
- Students burn out on the vault before they finish the curriculum
- The final Research Audit is never reached

**Prevention:**
1. **Explicit onboarding note: The Vault is a Tool, Not the Project.** Month 00 (Orientation) includes a note that says: "Your goal is to think better, not to have a perfectly organized vault. If you spend more than 15 minutes/week on vault maintenance, you're spending time you should spend learning. The provided folder structure works. Don't improve it until you've finished the curriculum."
2. **Template completeness.** Provide everything: folder structure, templates, frontmatter schemas, Dataview queries. The student should never need to create a new organizational structure. If they *want* to, they can — but it's explicitly optional.
3. **No custom CSS, no heavy theming.** The STACK.md already recommends against custom themes. Include this in onboarding.
4. **Monthly "workspace check" as a single bullet point.** "Did you spend more than 30 minutes on vault organization this month? If yes, skip next month's organizing and focus on content. The vault is fine as-is."
5. **One principle: "Better to capture imperfectly than not at all."** This should be a pull quote in the curriculum MOC.

**Detection:** Student asks "can I restructure the folders?" or "should I add a `#methodology` tag?" instead of asking content questions. Dataview query shows the student has modified templates but completed fewer than 50% of exercises.

**Phase to address:** Phase 0 (Onboarding/Setup) — orientation note. Phase 3 (Vault Hygiene, Month 04) — reframe maintenance as minimal discipline, not maximization.

---

### P8: Isolation Dropout — The Silent Killer of Self-Guided Programs

**What goes wrong:** Students start with enthusiasm, work through Month 01 alone, Month 02 alone, and by Month 03 the loneliness of solo learning catches up. Small obstacles feel insurmountable. Missed sessions pile up (P11). There's no one to say "I found that tricky too" to. Students drift away — not because the content is bad, but because learning alone is isolating.

**Why it happens:** This is the single most robust finding in online learning dropout research (Systematic reviews: Springer 2024, Springer 2022, PMC 2022 — all confirming isolation as a primary dropout predictor across 110+ studies). Online learning is structurally lonely. The curriculum is designed for a single Obsidian vault. There is no instructor, no cohort, no community. The problem is not content quality — it's environment.

**Consequences:**
- 50-80% attrition rates in self-guided programs without community structure
- Students don't quit dramatically — they fade quietly, feeling guilty
- The 3-5 hours/week feels like an impossible ask when there's no accountability
- Students who need the curriculum most (isolated early-career researchers) drop out first

**Prevention (the curriculum cannot fully solve this — it's a structural limitation — but can mitigate):**
1. **Built-in peer accountability prompts.** Every monthly review template includes: "If you have a colleague also doing this curriculum, schedule a 30-minute check-in to compare your Month X synthesis notes. If you don't, post in [forum] and find one."
2. **Suggested cohort formation.** The curriculum MOC includes a note: "This curriculum works best with a partner. Share the vault, set a weekly check-in, and discuss one exercise answer per week. Two people using the same vault creates 10x the learning."
3. **Community recommendation.** Recommend a forum, Discord, or Slack (but don't build one — out of scope per PROJECT.md). Point to existing communities: LessWrong, Effective Altruism Forum, Rethink Priorities, academic Twitter, or the student's own lab/department.
4. **Structured peer feedback in template design.** Paper Critique Worksheets include a "Peer Reviewer" field and a structured review section: "If you have a partner, swap critiques. Write your partner 3 specific questions about their analysis." This scaffolds peer interaction without requiring an instructor.
5. **The Human Voice Problem (P15 countermeasure).** Self-guided materials should include the instructor's voice — opinionated commentary, personal anecdotes about getting things wrong, warm phrasing that simulates presence. The vault shouldn't feel like a textbook; it should feel like a mentor who believes in you.
6. **Weekly email/notification not in scope** — but if possible, a simple calendar reminder template ("Every Sunday at 7pm, review this week") creates artificial structure.

**Detection:** Exercise response quality drops, then responses stop entirely. The student's Thinking Journal shows "fell behind" twice in a row. This is the leading indicator — intervene if there were a mechanism (there isn't in self-guided, which is why P8 is critical).

**Phase to address:** Phase 0 (Onboarding) — set expectations about community. Phase 2 (Content Authoring) — embed peer interaction prompts in templates. Phase 12 — if designing a cohort version later, this is the biggest leverage point.

---

### P12: The Deliberate Practice Gap — Passive Reading Without Skill-Forming

**What goes wrong:** The curriculum includes lesson notes that students read and perhaps highlight. But reading about critical thinking doesn't make you a critical thinker, any more than reading about piano makes you a pianist. Without *deliberate practice* — structured exercises at the edge of competence, with immediate feedback loops — students accumulate knowledge about CT but don't improve their CT ability.

**Why it happens:** This is a subtle re-incarnation of the Implicit Instruction Fallacy (P2). Curriculum authors write excellent explainer notes, assume understanding = skill acquisition, and then wonder why students can define all 40 biases but can't spot them in an unfamiliar paper. The lesson-template in STACK.md prioritizes content delivery ("lesson body") over practice design.

**Consequences:**
- Students can recite definitions from memory but score poorly on actual reasoning assessments
- The curriculum produces confident incompetence (Dunning-Kruger effect in CT itself)
- The Paper Critique Worksheets are completed with superficial analysis because the underlying reasoning muscles are underdeveloped
- By Month 12, students have "completed" the curriculum but haven't changed their research behavior

**Prevention (based on Ericsson's deliberate practice + van Gelder 2005):**
1. **Repurpose the ratio: spend 70% of time on exercises, 30% on reading.** Each lesson note should be short (500-700 words) — the bulk of study time should be in the associated exercise sheet. Currently, the template prioritizes the lesson body. Flip it.
2. **Exercise design must push past comfort.** Van Gelder: "Students will improve their critical thinking skills most effectively just to the extent that they engage in lots of deliberate practice." Exercises should be:
   - **At the edge of competence** (not too easy, not impossible)
   - **Self-correcting** (the student can check their answer against a provided model)
   - **Repeated with variation** (not the same exercise format every week)
   - **Evidence-tracked** (frontmatter captures scores, so students see their own learning curve)
3. **Embed immediate feedback.** Every exercise should have a "Compare with Model Answer" section. Not to penalize wrong answers, but to show *how* an expert reasoner approached the same problem. This is the closest thing to a tutor in a self-guided program.
4. **Weekly calibration tracking.** The weekly review should include: "What did I practice this week that was at the edge of my ability? What was too easy? What was too hard?"
5. **Template redesign.** The current Lesson Note template has 5 sections: Content, Takeaways, Apply It, Check Understanding, Related. The "Apply It" section is one bullet list. Restructure: the Exercise Sheet is the *primary* artifact; the Lesson Note is *pre-reading* for the exercise.

**Detection:** Students can explain the concept but their exercise scores are low. Learning objectives use "understand" instead of "apply" or "evaluate." Students report that exercises feel like "busywork" because they're too easy or too disconnected from the lesson.

**Phase to address:** Phase 2 (Content Authoring) — exercise design must be the primary authoring effort, not an afterthought. Phase 1 (Curriculum Design) — set the exercise-to-reading ratio as a design constraint.

---

## Moderate Pitfalls

### P9: Frontmatter Drift — Inconsistent Metadata Breaks Dashboards

**What goes wrong:** Over 12 months, students create hundreds of notes with frontmatter. Some notes have a `status` field, some don't. `status` is sometimes `completed`, sometimes `complete`, sometimes `done`. `tags` are sometimes an array, sometimes a single string. `month` is sometimes a number, sometimes a string `Month 01`. Dataview queries that worked in Month 03 break silently in Month 07 because the data shape changed.

**Why it happens:** No one notices the first inconsistency. The system works for months despite minor drift. Then a student copies an exercise note from Month 02 and modifies it in Month 08, inheriting old frontmatter conventions. Dataview queries return empty tables, and the student assumes the plugin broke rather than the data being inconsistent.

**Consequences:**
- Progress Dashboard shows incomplete counts (silently demotivating — you think you're behind)
- "Exercises due this week" queries miss entries with wrong status values
- Students lose trust in the Dataview system and stop using dashboards
- Vault feels broken even though all notes are present

**Prevention:**
1. **Templates are the single source of frontmatter.** Students never write frontmatter by hand — every note is created from a template that enforces the correct schema. This is already the plan in STACK.md.
2. **Template linting by Month 04.** The Vault Hygiene month includes a task: run a frontmatter consistency check using Dataview or the [Vault Physician](https://github.com/Tejaaswini/obsidian-plugin) plugin (or similar). Flag any note with missing required keys or unexpected values.
3. **Controlled frontmatter values.** Use `INPUT[inlineSelect]` in Meta Bind templates rather than free-text fields wherever possible. `status` should be `not-started | in-progress | completed` — never free text.
4. **Quarterly frontmatter audit as a curriculum activity.** Month 06 and Month 09 include a "Vault hygiene check" where students run a maintenance Dataview query to catch drift.

**Detection:** A Dataview query for "incomplete exercises" returns 0 results when you know you have 3 incomplete. Opening a few notes reveals that some use `status: done` instead of `status: completed`.

**Phase to address:** Phase 0 (Templates) — every template must have a complete, identical frontmatter schema. Phase 3 (Vault Hygiene, Month 04) — teach automatic detection.

---

### P10: Plugin Overprovisioning — Installing Tools Before Having the Problem

**What goes wrong:** Students see "recommended plugins" and install all of them before starting. They're distracted by learning 5+ plugin interfaces alongside the actual curriculum content. Each plugin adds cognitive overhead: "Where did that button go?" "Why is my vault slow?" "How does Dataview syntax work again?"

**Why it happens:** The STACK.md already provides a tiered recommendation and warns against this. But students, especially the tech-forward researchers who are the target audience, will install everything at once because they want "the full Obsidian experience." The 12-month duration amplifies this: if a plugin breaks during an update (see Technical Pitfalls), the student wastes a session debugging instead of learning.

**Consequences:**
- 2-3 hours lost to plugin configuration and learning curves in Month 01
- Excalidraw is explored for 2 hours before the first exercise is attempted
- A plugin update breaks something, and the student blames the curriculum
- Obsidian startup time increases (confirmed by Obsidian Forum: 4+ seconds for 8 plugins vs 0.3s for core)

**Prevention:**
1. **Start with Tier 1 only.** The Month 00 orientation note should say: "Install only Templater, Dataview, Meta Bind, and Obsidian Git. Use the curriculum for at least 2 months before adding any other plugins. If you find yourself thinking 'I wish I could ___', add it then. Otherwise, you're solving problems you don't have."
2. **Distribute the vault with the correct plugins pre-listed.** Include a `.obsidian/community-plugins.json` that lists only Tier 1 plugins. Students can add more later.
3. **Each plugin has a "When You'll Need It" note.** Dataview: "You'll start using this in Month 03 when we build your first progress query. Before that, it just sits there quietly."
4. **Obsidian Git's auto-commit is configured and forgotten.** Don't make students think about it. The STACK.md's `push on backup: enabled` is correct — set it and forget it.

**Detection:** Student asks "How do I use Excalidraw?" before the first exercise. Obsidian startup time > 3 seconds (measure: core + 4 plugins should be ~1 second on modern hardware).

**Phase to address:** Phase 0 (Onboarding/Setup) — pre-configure the vault with minimal plugins. Phase 2 (Content Authoring) — introduce plugins gradually as they become relevant.

---

### P11: The Pile-Up Effect — Falling Behind Creates Self-Reinforcing Disengagement

**What goes wrong:** A student misses Week 03 due to a conference. Week 04 assumes Week 03 concepts. The student now has 2 weeks of content to catch up on alongside current work. By Week 05, they have 3 weeks of backlog. The psychological weight of the pile makes returning feel impossible. The student drops out, not because the content is hard, but because catching up feels harder than quitting.

**Why it happens:** This is well-documented in the MOOC dropout literature as the "pile-up effect" (BrainCert 2026): only 36% of learners who drop out for a single week re-engage within two weeks. The longer the gap, the less likely return becomes. The curriculum's sequential design (Month 02 builds on Month 01) makes this worse — you can't skip ahead.

**Consequences:**
- Students who would have benefited most (busy researchers with unpredictable schedules) drop out first
- Curriculum completion is correlated with schedule stability, not with learning ability
- The 12-month design assumes continuous engagement, but real researcher life has grant deadlines, conference travel, teaching terms

**Prevention:**
1. **Two-month buffer built into the design.** Mark months as "Core" (required) and "Enrichment" (optional). Months 01, 04, 07, 10 are Core. Months 02-03, 05-06, 08-09, 11-12 are Enrichment. A student who falls behind in Month 02 can skip to Month 04 as long as they completed Month 01. This breaks the chain of dependency.
2. **Monthly MOCs include explicit "if you're behind" pathways.** "If you have only 2 hours this month, do lessons 1, 3, and 5 only. The rest are optional deep dives. You'll still be prepared for Month 04."
3. **Weekly review template includes a "skip without guilt" section.** "If you didn't complete everything, choose one incomplete item to carry forward. Mark the rest as 'deferred' and move on. Perfection is the enemy of progress."
4. **Curriculum MOC shows a minimum viable path.** A dataview query flags which lessons are required prerequisites for later months. Everything else is bonus.
5. **Obsidian Git's version history enables "restart from clean state."** If a student missed 3 months, they can revert to the Month X-1 state and restart.

**Detection:** Student's weekly reviews show "didn't complete" for 2+ consecutive weeks. Thinking Journal entries shift from content reflection to guilt/apology.

**Phase to address:** Phase 1 (Curriculum Design) — design the minimum viable path and mark dependencies explicitly.

---

### P13: Tag Sprawl — Proliferating Tags Without Standards

**What goes wrong:** Students add tags organically as they create notes. `#methodology`, `#methods`, `#research-methods` are all used for similar concepts. `#Bayesian` and `#bayes` and `#bayesian-stats` coexist. `#replication-crisis`, `#replication`, and `#reproducibility` are treated as separate categories. Over 12 months, the tag list grows to 100+ entries, many redundant, making the Tags pane useless for navigation.

**Why it happens:** Tags are cheap and additive. There's no cost to creating a new tag, so the tag set grows monotonically. The existing vault already uses specific tags (`cognitive-bias`, `claim`, `book`, `mental-models`, `forecast`), and the curriculum adds more (`lesson`, `exercise`, `curriculum`, `paper-critique`). Without maintenance, the tag set fragments.

**Consequences:**
- Dataview queries by tag become unreliable (querying `#bayes` misses notes tagged `#bayesian`)
- Tags pane becomes overwhelming (50 useful tags + 50 near-duplicates)
- Students stop using tags because "I can never find the right one"
- Frontmatter metadata quality degrades, compounding P9

**Prevention:**
1. **Controlled tag vocabulary in templates.** Every template hardcodes the tags that matter (`tags: [lesson, curriculum, month-01]`). Students never type free-text tags in curriculum notes.
2. **Policy: Tags describe what the note IS, not what it's ABOUT.** `#cognitive-bias` means "this note is a cognitive bias entry." Not "this note is about cognitive biases." The curriculum MOC links to biases; the notes themselves only tag by type. This matches the existing vault convention.
3. **Month 04 vault hygiene: tag audit exercise.** "Run a Dataview query that lists all tags used fewer than 3 times. For each, either remove it or merge it into a more common tag."
4. **Vault Physician or similar tag-merge tool as optional.** Recommend for Month 06 if tag count exceeds 40.

**Detection:** Student creates a new tag for every exercise. Dataview `LIST tags` returns tags used once.

**Phase to address:** Phase 0 (Templates) — enforce tag vocabularies in template frontmatter. Phase 3 (Vault Hygiene, Month 04) — teach tag maintenance.

---

### P14: Procrustean Sequencing — Forcing a Fixed Path When Learners Need Flexibility

**What goes wrong:** The curriculum assumes all students progress linearly through 12 months. But researchers enter with vastly different backgrounds: a statistics PhD has different needs than a humanities postdoc. Forcing everyone through the same sequence creates boredom for advanced students and overwhelm for novices.

**Why it happens:** It's easier to write one curriculum than to design branching paths. The PROJECT.md's "spiral curriculum" idea correctly suggests revisiting topics, but it still assumes everyone spirals from the same starting point.

**Consequences:**
- Statistically sophisticated students resent spending Month 04 on probability foundations
- Students with no logic background are lost in Month 02
- The curriculum serves neither group well
- Completion is correlated with entry knowledge, not with learning

**Prevention:**
1. **Self-assessment entry quiz at Month 00.** A 15-question diagnostic covering: argument identification, probability concepts, bias awareness, statistical literacy. Results recommend a starting month. Score >80%? Start at Month 04. Score 50-80%? Start at Month 02. Score <50%? Start at Month 01.
2. **Acceleration tracks within each month.** Lessons are labeled `foundational`, `core`, and `advanced`. Advanced students skip foundational, do core, and take the advanced option on exercises. Novices do all three layers.
3. **Monthly MOC has a "prerequisites" box.** "You need these concepts from earlier months. If you're confident in them, skip the review links. If not, start there."
4. **The research focus is the fixed point, not the month number.** Every student does Month 12 (Research Audit) with their own papers. The earlier months are means to that end, not ends in themselves.

**Detection:** Student feedback: "This is too basic" or "I'm lost." Beta testing with diverse researchers reveals wide variance in completion times for the same month.

**Phase to address:** Phase 1 (Curriculum Design) — design tiered content and entry assessment. Phase 2 (Content Authoring) — write each lesson with multiple entry points.

---

### P15: The Black Screen of Isolation — No Human Voice in Self-Guided Materials

**What goes wrong:** The curriculum is text-only, templated, and efficient. Every lesson reads like a technical manual. Students feel they're learning from a faceless system. Small frustrations (confusing exercise, unclear instruction) become big blockers because there's no one to ask.

**Why it happens:** The curriculum authors are academics writing in academic style (passive voice, hedged claims, citation-heavy). The templates encourage consistency but not voice. The result is a "textbook in Obsidian" — accurate, sterile, and unengaging.

**Consequences:**
- Students feel unsupported and alone (amplifies P8)
- Ambiguities in lesson instructions become deal-breakers instead of minor confusions
- The curriculum feels like a chore rather than a mentorship
- Students disengage at the first point of friction

**Prevention:**
1. **Write in first person with personality.** "I've been teaching this stuff for years, and here's the mistake almost everyone makes on their first try..." This is already partially present in the existing Critical Thinking.md's voice ("surprisingly deep once you study it seriously"). Extend this to all curriculum content.
2. **Include "Dear Researcher" letters at month starts.** A 200-word note from the author describing: what surprised them when learning this topic, a personal failure story, and encouragement for the month ahead. This costs nothing to write and pays huge dividends in perceived support.
3. **Anticipate confusion points.** Every exercise should include: "If you're stuck, here are three things to try before giving up." This simulates having a TA.
4. **Record the author's voice once.** Even though video is out of scope, a single 5-minute "welcome to the curriculum" audio file embedded in the vault would establish a human presence for the entire 12 months.
5. **Conversational tone, not academic.** Use contractions, rhetorical questions, and second-person address. Review each lesson for: "Would I say this to a student sitting across from me?"

**Detection:** Beta readers describe the content as "dry" or "like a textbook." Students report feeling "stuck" without describing what they're stuck on.

**Phase to address:** Phase 2 (Content Authoring) — tone review pass after content drafting.

---

### P16: Final-Stretch Dropout — No Climax in Months 10-12

**What goes wrong:** Months 01-09 build knowledge progressively. Month 10 looks like Month 09 — more lessons, more exercises, another MOC. There's no sense of building toward something. Students who have been diligent for 9 months lose momentum just before the finish.

**Why it happens:** The curriculum is designed as a steady march. But human motivation needs peaks and valleys. Month 12 is described as "Integration & Research Audit" — which sounds like just another topic module rather than a culminating event.

**Consequences:**
- Students stop at Month 09 or 10, just before the integration phase that ties everything together
- The Research Audit, the most valuable artifact, is never completed
- Students feel their 9 months of effort was wasted because they never reached synthesis
- The curriculum is rated "incomplete" even though they did most of it

**Prevention (SheTalks 2026 — "final-stretch dropout" pattern):**
1. **Month 10 is a "peak" event, not a continuation.** Design Month 10 as a milestone: "First Complete Paper Audit." Students produce their first full Research Audit of a paper in their field. It's messy and imperfect — that's the point.
2. **Month 11 is a "valley" — consolidation and gap-filling.** After the high of Month 10, Month 11 is lighter: reviewing what the Month 10 audit revealed, revisiting weak areas, optional deep dives.
3. **Month 12 is a "peak" — the final Research Audit.** The student audits a paper of their choice using all 11 preceding months' skills. They write a structured critique, compute Brier scores for their forecasts, and produce a "thinking self-assessment." This is the capstone.
4. **Explicit finish-line.** Month 12's MOC should prominently count down: "You are here. 4 lessons to go. You have done 95% of the work. The last 5% is the most valuable."
5. **Certificate of completion (even a markdown note).** A templated "Certificate of Completion" note that the student generates from a template after finishing the final exercise. This provides a psychological endpoint.

**Detection:** Exercise completion rates drop steadily from Month 09 to Month 12.

**Phase to address:** Phase 1 (Curriculum Design) — design the emotional arc, not just the content arc. Months 10-12 must have different pacing and stakes than Months 01-09.

---

### P17: Folder Maximalism — Nested Hierarchies That Become Burial Grounds

**What goes wrong:** Students, especially those coming from hierarchical tools (Notion, Evernote, file explorers), create deep folder nests. `Paper Reviews/Sci 2026/Q1/Neuroscience/Cognition/Working Memory/preprint.md`. Notes at the bottom of these trees are never found again. The folder hierarchy becomes a filing cabinet where files go to die.

**Why it happens:** It's the default mental model of organization — put things in categories. Obsidian's linking model makes folders optional, but the habit is hard to break. The curriculum's existing structure (`Curriculum/Month XX/Exercises/`) is already 3 levels deep, which is borderline.

**Consequences:**
- Notes are filed but never retrieved
- Graph view becomes incomplete (notes exist but aren't linked)
- Students feel their vault is "messy" and reorganize (wasting time — P7)
- The curriculum's folder structure, meant to be helpful, becomes a labyrinth

**Prevention:**
1. **Shallow hierarchy enforced by the curriculum's own structure.** Max 2 levels deep: `Curriculum/Month 01/`, `Curriculum/Month 01/Exercises/`. No deeper. Students' own notes (paper reviews, journal entries) follow the existing vault's flat structure.
2. **"Folders are for location, links are for context."** This maxim (from Obsidian community best practices) should be in the orientation. Folders tell you where a file is; links tell you what it means.
3. **Monthly review includes a "folder audit."** "Are there any folders more than 2 levels deep? If yes, flatten them. A note's value is in its links, not its folder location."
4. **Search over navigation.** The curriculum teaches: "Use search (Cmd/Ctrl+P) to find notes, not the file explorer. If you can't find a note by searching, fix its title, not its folder."
5. **No PARA or custom organizational systems.** The curriculum provides the structure. Students should not feel the need to impose their own on top of it.

**Detection:** A student's file explorer shows folders with only 1-2 notes each. "Where did I put that paper critique from Month 05?" requires 30 seconds of navigation.

**Phase to address:** Phase 0 (Onboarding) — set folder philosophy. Phase 3 (Vault Hygiene, Month 04) — reinforce with folder audit exercise.

---

### P18: Belief Preservation Blind Spot — Failing to Address Resistance to Evidence

**What goes wrong:** The curriculum teaches critical thinking as a purely cognitive skill, ignoring the emotional and identity-based reasons that researchers resist updating their beliefs. Students can pass all the logic exercises but still protect their pet hypotheses from evidence — because the curriculum never addressed *why* smart people resist changing their minds.

**Why it happens:** This is the most commonly overlooked dimension in CT curricula (van Gelder 2005 flags it specifically). CT is typically taught as "here's how to think correctly," assuming that knowing the right way leads to doing the right way. But belief preservation (myside bias, identity-protective cognition, motivated reasoning) operates below the level of conscious reasoning.

**Consequences:**
- Students apply critical thinking to other people's papers but not to their own work
- The entire replication crisis module is consumed as "interesting" without personal behavioral change
- Students audit papers for statistical rigor but don't examine their own theoretical commitments
- The curriculum produces better critics but not better scientists

**Prevention:**
1. **Explicit month on "Thinking About Your Own Thinking."** Month 08 (placed after the normative models are established but before integration) should focus on metacognition, identity-protective cognition, and strategies for making yourself wrong.
2. **"Find a time you were wrong" exercise.** Month 05: "Find a paper from 2+ years ago that changed your mind about something significant. Write a structured reflection: What did you believe? What evidence changed it? What would it have taken to change your mind sooner?"
3. **Adversarial collaboration exercises.** "Take a claim you strongly believe about your research. Write the strongest 500-word argument against it. Then have a colleague read it and tell you where you pulled your punches."
4. **Pre-mortem and post-mortem templates.** Before starting a study: "What would it mean if this hypothesis were false? What evidence would convince me?" After: "Where did I protect my prior beliefs?" This is a Research Audit dimension.
5. **Curve your own calibration.** Monthly calibration tracking (forecasts vs. outcomes) is already planned. Extend it: "Looking back at your predictions from last month, which ones did you update appropriately? Which ones did you cling to past the evidence?"

**Detection:** Student can identify motivated reasoning in others but not in themselves. The Thinking Journal shows no entries about being wrong.

**Phase to address:** Phase 1 (Curriculum Design) — must be designed into the sequence, not added as an afterthought. Phase 2 (Content Authoring) — write the metacognitive month with care.

---

### P19: Syncing on Network Drives — Vault Corruption Over 12 Months

**What goes wrong:** A student stores the vault on iCloud, Dropbox, Google Drive, or OneDrive for cross-device access. In Month 06, after saving a note, a sync conflict creates a duplicate file. Or two devices write simultaneously, corrupting a file. Or the network drive's file-locking causes Obsidian to read stale data. Weeks of work are lost.

**Why it happens:** This is a widely documented Obsidian issue (Obsidian Forum, STACK.md anti-recommendations). Cloud sync services are not designed for the concurrent-write patterns of Obsidian (many small files, frequent saves, simultaneous device access). The warning is already in STACK.md, but students won't read it until it's too late.

**Consequences:**
- Loss of weeks of curriculum work
- Students blame Obsidian and abandon the vault
- If syncing with a team (lab mates), corruption propagates to everyone
- Trust in the curriculum is destroyed

**Prevention:**
1. **Obsidian Git as the ONLY sync mechanism.** The Month 00 orientation should say: "If you want your vault on multiple devices, use Obsidian Git with a private GitHub/GitLab repository. Do NOT use iCloud, Dropbox, Google Drive, or OneDrive for the vault folder. This is not negotiable. These services will corrupt your vault over 12 months."
2. **Ship the vault with Obsidian Git pre-configured with an explanatory note.** "The git integration is your backup AND your cross-device sync. Commit often, push when you switch devices, pull when you resume."
3. **If student insists on cloud sync, provide a "safe syncing" guide.** "Set Obsidian Git to auto-commit every 30 minutes. Disable your cloud sync for the vault folder. Only sync via git. Cloud sync will eventually break your vault — it's a question of when, not if."
4. **Avoid Obsidian Sync for high-stakes content.** The STACK.md notes it's available. It's safer than iCloud but still has corruption edge cases. Recommend git as primary.
5. **Test the vault distribution process.** When a student downloads the curriculum as a `.zip`, the `.obsidian/` config must be preserved so plugins are ready.

**Detection:** (Catastrophic — detected after data loss) Student says "my vault files got corrupted."

**Phase to address:** Phase 0 (Onboarding/Setup) — this must be communicated clearly before the student writes their first note.

---

### P20: Missing Formative Assessment — No Checkpoints Before It's Too Late

**What goes wrong:** The curriculum provides exercises and a final Research Audit, but there are no intermediate checkpoints where the student can gauge whether they're on track. By the time they realize they misunderstood Bayesian updating (Month 06), the error has propagated through 3 months of work.

**Why it happens:** Self-guided curricula default to "read → do exercise → move on." But exercises measure whether the student *completed* the activity, not whether they *understood* the concept. Without a "check your understanding" mechanism that provides a clear yes/no on conceptual mastery, students proceed with misconceptions silently compounding.

**Consequences:**
- Students build on faulty foundations
- The Month 12 Research Audit reveals systematic errors that could have been caught in Month 03
- Students feel the curriculum "failed them" (it did — by not providing formative feedback)
- Repeated failure at advanced stages causes P8 dropout

**Prevention:**
1. **End-of-month "mastery check."** Each month ends with 5 short-answer questions or a mini-case analysis that the student can compare against a model answer. "Mastery = at least 4/5 aligned with the model." If not, the student gets a targeted "review these lessons" recommendation.
2. **Cumulative checkpoints at Months 03, 06, 09.** A 15-question diagnostic covering all prior material. This is not graded — it's for the student's self-assessment. Includes a "remediation path" for each weak area.
3. **Calibration tracking as formative feedback.** The existing calibration exercise (forecasts → outcomes → Brier scores) IS formative assessment. But it needs to be explicitly framed as such: "Your calibration curve tells you where your probability estimates are biased. If your curve is consistently overconfident, review Month 04's section on base rates."
4. **Self-check criteria in every exercise.** The template currently has 3 checkboxes. Expand: "Rate your confidence in each answer: high/medium/low. Then compare with the model. If your confidence was high and your answer was wrong, flag this concept for review."
5. **"Teach it to a colleague" as a mastery test.** "After this month, find a colleague and explain [core concept] in 5 minutes. If you can't, you haven't mastered it yet. Review lessons 2 and 4 before proceeding."

**Detection:** Students report "I thought I understood it until I tried the Research Audit." Exercise scores are high (completion-based) but concept application is low (transfer-based).

**Phase to address:** Phase 2 (Content Authoring) — write mastery checks and model answers alongside lesson content, not as an afterthought.

---

## Minor Pitfalls

### Folder Structure Anti-Patterns

| Pitfall | What Goes Wrong | Prevention |
|---------|----------------|------------|
| Number-only filenames (`01.md`, `02.md`) | Graph view shows meaningless labels; sorting works but discovery doesn't | Already prevented by STACK.md convention `MM.NN - Title.md` |
| Mixing curriculum and reference content | Impossible to cleanly remove curriculum from vault | Already prevented by `Curriculum/` top-level directory |
| Single massive MOC | Information overload; students skip it | Already prevented by monthly MOCs with progressive scope |
| Canvas as navigation | Corruptible JSON; can't be queried; fragile | Already noted as anti-pattern in STACK.md — use MOCs instead |
| Obsidian Publish for distribution | Interactive widgets (Meta Bind) don't work on published sites | Already noted in STACK.md — distribute vault as zip/git |

### Template Anti-Patterns

| Pitfall | What Goes Wrong | Prevention |
|---------|----------------|------------|
| Templates that add overhead without value | Student spends 5 minutes filling frontmatter for a 2-minute journal entry | Template frontmatter should have at most 5 fields. Journal template especially — just `tags` and `date`. |
| Rigid templates that don't fit the content | Student skips sections or modifies structure | Each template section should be optional. If a lesson doesn't need a "Prerequisites" section, delete it. |
| Templater overuse | Template errors when file naming doesn't match expectations | Test every template against edge cases (no month number in path, no title provided). Provide fallback values. |

### Dataview Anti-Patterns

| Pitfall | What Goes Wrong | Prevention |
|---------|----------------|------------|
| Excessive dataviewjs | Breaks on plugin updates; non-portable | Already flagged in STACK.md — use DQL for 95% of queries |
| Queries without error handling | Empty table when frontmatter field is missing | Every student-facing query should include an empty-state message: "No incomplete exercises. Great work!" |
| Queries that expose every note | Scrolling through 200 results is useless | Limit to current month: `FROM "Curriculum/Month 01"` |

### Authoring Process Anti-Patterns

| Pitfall | What Goes Wrong | Prevention |
|---------|----------------|------------|
| Writing all lessons in linear order before reviewing | Curriculum imbalance — too much content in early months, burn-out in later | Write Month 01 and Month 12 first. These define the beginning and end. Then fill middle months. |
| No beta testing before release | Undiscovered inconsistencies, confusing instructions, wrong pacing | Beta test Month 01-03 with 3-5 researchers. Time their completion. Interview for confusion points. |
| Writing for "average researcher" | Satisfies no one | Design for the range: foundational, core, advanced tiers within each lesson. |
| Treating the curriculum as done at launch | Content drift, broken links, outdated plugin versions | Schedule quarterly review cycles (PROJECT.md's "Evolution" section is the right approach — enforce it). |

---

## Phase-Specific Warnings

| Phase Topic | Likely Pitfall | Severity | Mitigation |
|-------------|---------------|----------|------------|
| **Phase 0: Onboarding/Setup** | Students install too many plugins (P10) | MEDIUM | Pre-configure vault with Tier 1 only; orientation note with anti-install advice |
| **Phase 0: Onboarding/Setup** | Students use iCloud/Dropbox sync (P19) | CRITICAL | Orientation must be explicit: "git or nothing" |
| **Phase 1: Curriculum Design** | Aboutness Trap — curriculum as topic survey (P1) | CRITICAL | Define program-level outcome first; each month must be a skill-building arc |
| **Phase 1: Curriculum Design** | Wrong sequencing (P5) | CRITICAL | Follow the normative-first order; validate against existing curricula |
| **Phase 1: Curriculum Design** | No entry assessment / Procrustean sequencing (P14) | MEDIUM | Include diagnostic quiz and tiered content |
| **Phase 2: Content Authoring** | Cognitive overload / too much per lesson (P4) | CRITICAL | Enforce time budgets; one-screen-one-point rule |
| **Phase 2: Content Authoring** | Passive reading without skill practice (P12) | HIGH | 70% exercise / 30% reading ratio |
| **Phase 2: Content Authoring** | No mastery checks / formative assessment (P20) | HIGH | Every month needs end-of-month check with model answer |
| **Phase 2: Content Authoring** | Sterile voice / no human presence (P15) | HIGH | Include author voice, "Dear Researcher" letters, failure stories |
| **Phase 2: Content Authoring** | Domain-general fallacy / no field scaffolding (P3) | CRITICAL | Dual-exercise design; domain bridge templates |
| **Phase 3: Vault Hygiene (Month 04)** | Orphan rot (P6) | HIGH | Orphan detection taught as a meta-skill; linking scaffolding in templates |
| **Phase 3: Vault Hygiene (Month 04)** | Frontmatter drift (P9) | MEDIUM | Frontmatter linting exercise; controlled vocabularies |
| **Phase 3: Vault Hygiene (Month 04)** | Tag sprawl (P13) | MEDIUM | Tag audit; controlled vocabularies in templates |
| **Phase 4+: Ongoing Engagement** | Isolation dropout (P8) | CRITICAL | Peer accountability prompts; cohort recommendations; author voice |
| **Phase 4+: Ongoing Engagement** | Pile-up effect (P11) | HIGH | Minimum viable paths; skip-without-guilt sections; buffer months |
| **Phase 10-12: Integration** | Final-stretch dropout (P16) | HIGH | Design emotional arc; Month 10 peak, Month 11 valley, Month 12 peak |
| **Phase 10-12: Integration** | Belief preservation not addressed (P18) | CRITICAL | Month 08 dedicated to metacognition and identity-protective cognition |
| **All Phases** | Vault perfectionism instead of learning (P7) | HIGH | Orientation framing; "capture imperfectly" principle |
| **All Phases** | Folder maximalism (P17) | MEDIUM | Shallow hierarchy; "folders for location, links for context" |

---

## Pitfall Interaction Map

Some pitfalls amplify each other. Understanding these interactions helps prioritize prevention:

```
P2 (Implicit Instruction) ──► P12 (Deliberate Practice Gap) ──► P3 (Domain-General)
        │                                                              │
        ▼                                                              ▼
P1 (Aboutness Trap) ──► P4 (Cognitive Overload) ──► P11 (Pile-Up) ──► P8 (Isolation Dropout)
                                                            ▲
P14 (Procrustean Sequencing) ──► P16 (Final-Stretch Dropout)
                                                            │
P18 (Belief Preservation) ──► P8 ──► (non-completion)

P6 (Orphan Rot) ◄──► P9 (Frontmatter Drift) ◄──► P13 (Tag Sprawl)
        │
        ▼
P7 (Vault Perfectionism) — wastes time, displaces learning

P15 (No Human Voice) ──► P8 (Isolation)
P19 (Cloud Sync) ──► (data loss) ──► P8
```

**Critical cascade to watch for:**
1. P1 (Aboutness) + P2 (Implicit) + P4 (Overload) = curriculum that teaches a lot of material but produces no skill improvement
2. P8 (Isolation) + P11 (Pile-Up) + P15 (No Voice) = the student quits by Month 03
3. P6 (Orphan) + P9 (Drift) + P13 (Sprawl) = by Month 08, the vault dashboard is broken and the knowledge graph is meaningless

**Break the cascade at:**
- P1 (Curriculum Design) — the most upstream prevention
- P8 (Engagement) — the most impactful downstream intervention
- P6 (Vault Hygiene, Month 04) — the most teachable vault-maintenance skill

---

## Sources

| Source | Key Findings Used | Confidence |
|--------|-------------------|------------|
| [Willingham, D.T. (2008). Critical Thinking: Why Is It So Hard to Teach?](https://www.aft.org/sites/default/files/media/2014/Crit_Thinking.pdf) | CT is not a general skill; domain knowledge interdependence; metacognitive strategies vs. actual ability | HIGH |
| [van Gelder, T. (2005). Teaching Critical Thinking: Some Lessons From Cognitive Science](https://people.bath.ac.uk/edspd/Weblinks/PGCES%20ULL%20articles/Learning%20to%20Learn/van%20Gelder%202005%20CT.pdf) | Deliberate practice essential; argument mapping; belief preservation; theory must accompany practice | HIGH |
| [Stanford Encyclopedia of Philosophy (Spring 2026). Critical Thinking: Educational Methods](https://plato.stanford.edu/archives/spr2026/entries/critical-thinking/methods.html) | Mixed approach (general + infusion) best evidence; institutional implementation difficulties; Paul-Elder framework adoption | HIGH |
| [Frontiers in Education (2026). From implicit to explicit: overcoming common barriers to teaching critical thinking](https://www.frontiersin.org/journals/education/articles/10.3389/feduc.2026.1689765/full) | Implicit instruction perpetuates inequity; explicit CT definition needed; scalable module approach | HIGH |
| [MoreBetterLabs (2026). The 2 Traps That Kill Online Courses](https://morebetterlabs.com/learning-design/the-two-traps-that-kill-online-courses/) | Aboutness Trap, Instructionism Trap, Dual Minimalism framework | MEDIUM (blog, but corroborated by academic sources) |
| [She Talks (2026). Why Experts Build the Worst Online Courses](https://shetalksmag.com/2026/03/why-experts-build-worst-online-courses/) | Overwhelm, invisible progress, isolation, final-stretch dropout patterns | MEDIUM (practitioner, but specific and actionable) |
| [BrainCert (2026). Why Learners Drop Off](https://blog.braincert.com/why-learners-drop-off-and-how-to-stop-it/) | Pile-up effect (36% re-engagement stat); social isolation as dropout driver | MEDIUM (practitioner, cited research) |
| [Springer (2024). Dropout in online higher education: a systematic literature review](https://link.springer.com/article/10.1186/s41239-024-00450-9) | Isolation, screen fatigue, academic workload as primary dropout factors across 110 studies | HIGH |
| [NIH/PMC (2022). Persistence and Dropout in Higher Online Education](https://pmc.ncbi.nlm.nih.gov/articles/PMC9197481/) | Feedback insufficiency; social connectedness as persistence factor | HIGH |
| [Critical Thinker Academy — Where to Start](https://criticalthinkeracademy.teachable.com/p/where-to-start) | Curriculum sequencing: logic before biases, probability foundations before Bayesian reasoning | MEDIUM (practitioner, but aligns with academic consensus) |
| [UC Berkeley Sense & Sensibility & Science](https://sensibility.berkeley.edu/index.php?title=Topics_and_lesson_plans) | Sequence: uncertainty → probabilistic reasoning → calibration → biases → causation → blinding → scientific reasoning | HIGH |
| [Obsidian Forum — Large Vault Performance](https://forum.obsidian.md/t/can-obsidian-handle-100s-of-thousands-of-notes/112785) | Sync issues with large vaults; graph view slowdown; folder move lockups | HIGH |
| [Obsidian Forum — Performance Issues](https://forum.obsidian.md/t/performance-on-large-vaults/114864) | Plugin startup time accumulation; recommendation to minimize plugins | HIGH |
| [Vault Physician Plugin](https://github.com/Tejaaswini/obsidian-plugin) | Orphan notes, frontmatter drift, tag sprawl decay patterns (20-30% orphan rate at 400+ notes) | HIGH (verified codebase + vault health data) |
| [Vault Plus Plugin](https://github.com/jabaho9523/obsidian-vault-plus) | Vault rot universal past ~200 notes; seven categories of structural decay | HIGH |
| [MakeUseOf (2026). 5 Beginner Mistakes That Made Obsidian Harder](https://www.makeuseof.com/beginner-mistakes-obsidian/) | Plugin overprovisioning; folder maximalism; linking too late | MEDIUM (practitioner) |
| [MakeUseOf (2026). Stopped Building Perfect Obsidian Vault](https://www.makeuseof.com/stopped-building-perfect-obsidian-vault-use-it-for-one-thing/) | Vault perfectionism; installing plugins before having the problem | MEDIUM (practitioner) |
| [XDA (2026). I Used Obsidian Wrong for a Year](https://www.xda-developers.com/used-obsidian-wrong-for-year-folder-setup-that-finally-clicks/) | Folders for location, links for context; flat hierarchy; tag as filter | MEDIUM (practitioner) |
| [Homeschool Tools — Logic & Critical Thinking Curriculum Guide](https://homeschooltools.net/subject/logic-critical-thinking) | Sequence: reasoning foundations → informal logic → formal logic → philosophy → computational thinking | MEDIUM (practitioner) |
| [Critical Thinkers Toolkit (SEA Homeschoolers, 2026)](https://seahomeschoolers.com/blog/2026/01/07/critical-thinking-as-content/) | Sequential, explicit skills instruction; frontloading prerequisite skills | MEDIUM (practitioner, cites curriculum research) |

---

*Pitfalls research for: Obsidian-based critical thinking curriculum*
*Researched: 2026-06-14*
*Confidence: HIGH — critical pitfalls verified against academic sources, domain pitfalls verified against existing curricula, technical pitfalls verified against Obsidian community data*
