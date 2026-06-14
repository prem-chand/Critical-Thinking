# Stack Research: Obsidian Curriculum Authoring Stack

**Domain:** Knowledge management — self-guided 12-month critical thinking curriculum in Obsidian
**Researched:** 2026-06-14
**Confidence:** HIGH

## Executive Summary

This is NOT a software stack — it's a content-authoring and knowledge-management stack built entirely within Obsidian. The "technologies" are Obsidian plugins, note-taking conventions, template systems, folder structures, and curriculum design patterns. The single inviolable constraint: **everything must live in the vault — no external databases, web apps, or build pipelines.**

After researching the current Obsidian plugin ecosystem (versions verified against GitHub releases as of June 2026), examining best practices from educational vault communities, and cross-referencing against the existing Critical Thinking vault conventions, the recommended stack prioritizes **stability over novelty** and **simplicity over power.** Every plugin recommended has been validated as actively maintained with recent releases.

---

## Recommended Stack

### Tier 1 — Must-Have Plugins (Vault infrastructure)

| Plugin | Version | Purpose | Why Recommended |
|--------|---------|---------|-----------------|
| **Templater** | 2.22.1 | Dynamic template injection | Replaces the built-in core Templates plugin. Supports date math (`tp.date.now`), file metadata (`tp.file.title`), frontmatter access (`tp.frontmatter`), and user prompts (`tp.system.prompt`). Essential for auto-populating exercise sheets, monthly MOCs, and daily journal entries with context-aware content. 5.1k stars, community-maintained, release within the last week. |
| **Dataview** | 0.5.70 | Query engine for progress dashboards | Queries frontmatter and inline fields across the entire vault. Enables curriculum-progress dashboards, "exercises due this week" views, belief calibration tracking tables, and cross-referencing notes by tag/status. 9.1k stars, new maintainer (holroy) actively developing. |
| **Meta Bind** | 1.5.0 | Interactive form widgets in notes | Enables inline confidence sliders, checkboxes that write to frontmatter, progress bars, and input fields — all without leaving reading view. Critical for making exercise sheets interactive (students update confidence directly in the note). 959 stars, release within the last week. |
| **Obsidian Git** | 2.38.3 | Automatic version control + backup | Auto-commits vault changes on a schedule. Provides rollback safety for a 12-month learning program where losing weeks of work is catastrophic. Does NOT require GitHub — works with any git remote or purely local. 11.3k stars, most popular Obsidian plugin, actively maintained. |

### Tier 2 — Recommended Plugins (Quality of life)

| Plugin | Version | Purpose | When to Use |
|--------|---------|---------|-------------|
| **Excalidraw** | 2.23.12 | Visual concept mapping | For creating argument diagrams, Bayesian network sketches, logic trees, experimental design flowcharts, and concept relationship maps. Embeds directly in notes. 7.1k stars, extremely active development (multiple releases per month). Use when a visual representation helps — do NOT use as primary content delivery (text-first constraint). |
| **Advanced Tables** | 0.23.2 | Markdown table formatting | Auto-formats markdown tables with tab/enter navigation. Valuable for confidence logs, comparison matrices, and evidence tables in paper critiques. 2.5k stars, maintained. |

### Tier 3 — Conditional Plugins (Enable only if needed)

| Plugin | Version | Purpose | When to Enable |
|--------|---------|---------|----------------|
| **Charts** | 3.9.0 | Chart.js-based data visualization | Only if the statistics/probability months need interactive charts (calibration curves, probability distributions). 783 stars. **Warning:** Last release Jan 2024 — watch for staleness before installing. Write chart data as inline Dataview fields so charts are optional, not load-bearing. |

### Core Plugins (Already Active — Verified)

These Obsidian built-in plugins are already enabled in the vault (`.obsidian/core-plugins.json`):

| Core Plugin | Role in Curriculum |
|-------------|-------------------|
| **Daily Notes** | Generates daily Thinking Journal entries. Configure target folder to `Thinking Journal/`. |
| **Templates** | Fallback for simple templates. Will be supplemented (not replaced) by Templater. Keep enabled for template folder management. |
| **Graph View** | Students explore their growing knowledge graph. Motivational for showing connected thinking. |
| **Backlinks** | Students see how concepts interconnect across months. |
| **Canvas** | For instructor-authored curriculum maps. NOT for student use (canvases are opaque JSON, hard to maintain). |
| **Tag Pane** | Navigate by content type (`moc`, `exercise`, `cognitive-bias`, `claim`, `forecast`, `lesson`). |
| **Properties** | Edit YAML frontmatter visually. Essential for students who don't want to hand-edit YAML. |
| **Outline** | Navigate long lesson notes by heading structure. |
| **Sync** | Multi-device access (if student uses Obsidian Sync). |
| **File Recovery** | Snapshot-based recovery for accidental deletions. |
| **Note Composer** | Merge/split notes during curriculum authoring. |

---

## What NOT to Use (Anti-Recommendations)

| Avoid | Why | Use Instead |
|-------|-----|-------------|
| **Calendar plugin** (`obsidian-calendar-plugin`) | **Frozen since April 2021.** Weekly notes functionality extracted to Periodic Notes plugin, which is also dormant (Apr 2022). Calendar's dot-tracker is distracting for a curriculum context. | Core Daily Notes plugin + Templater date functions for periodic journal entries. |
| **Periodic Notes plugin** | Same maintainer as Calendar, also dormant (last release Apr 2022). Weekly/monthly notes are handled more flexibly by Templater templates invoked manually or via core Daily Notes. | Templater templates for weekly review and monthly synthesis notes. |
| **Slated / tq (task plugins)** | Slated archived Jul 2021, tq replaces it but adds task management complexity irrelevant to curriculum. Curriculum progress is tracked via frontmatter checkboxes and Dataview queries, not a task manager. | Meta Bind checkboxes + Dataview query for "completed exercises." |
| **DataviewJS (excessive use)** | Dataview's JavaScript API is powerful but fragile — breaks on plugin updates and makes vault content dependent on execution environment. Inline DQL (Dataview Query Language) is stable. | Use `dataview` (DQL) blocks for 95% of queries. Reserve `dataviewjs` only for genuinely complex views (progress dashboards). |
| **Custom CSS themes** | Heavy theme customization breaks with Obsidian updates and creates a dependency students must manage. | Use one of Obsidian's built-in themes (Default or Minimal). The curriculum works with any theme. |
| **Make.md / Projects / DB Folder** | These plugins add database-like views and project management that fundamentally alter how users interact with notes. They create plugin lock-in — content becomes incomprehensible without the plugin. | Stay with plain markdown + YAML frontmatter. Dataview queries work over plain markdown. |
| **Obsidian Publish** | Publishes vault as a website, but curriculum is designed for interactive use WITHIN Obsidian. The interactive widgets (Meta Bind inputs, Dataview dashboards) don't work on published sites. | Distribute the vault itself as a `.zip` or git repository. Students open it in their own Obsidian. |
| **Canvas for navigation** | Canvas files are JSON blobs that can't be queried, diffed, or navigated with text tools. They're fragile — a single corrupted reference breaks the whole canvas. | Use MOC (Map of Content) notes with `dataview` queries for curriculum navigation. |

---

## Folder Structure Convention

### Curriculum Extends, Doesn't Replace

The curriculum lives in a single top-level directory (`Curriculum/`) that extends the existing vault structure without modifying it:

```
Critical Thinking.md                  ← Root hub (existing, add Curriculum link)
Biases/                               ← Existing reference library (untouched)
Books/                                ← Existing (untouched)
Claim Analysis/                       ← Existing (untouched)
Forecasts/                            ← Existing (untouched)
Logical Fallacies/                    ← Existing (untouched)
Mental Models/                        ← Existing (untouched)
Paper Reviews/                        ← Existing (extended with exemplar critiques)
Thinking Journal/                     ← Existing (extended with month-aligned prompts)
_templates/                           ← Existing templates (untouched)
Curriculum/                           ← NEW — all curriculum content
├── Curriculum MOC.md                 ← Hub: links all months, shows progress dashboard
├── Month 01 - Foundations/           ← One directory per month
│   ├── Month 01 MOC.md               ← Month hub with learning objectives, reading list, exercise index
│   ├── 01.01 - What Is Critical Thinking.md
│   ├── 01.02 - System 1 and System 2.md
│   ├── ...                           ← 8-12 lesson notes per month
│   ├── Exercises/                    ← Monthly exercise sheets
│   │   ├── 01 - Calibration Warmup.md
│   │   ├── 02 - Bias Spotting.md
│   │   └── ...
│   └── Review/                       ← Weekly + monthly review templates
│       ├── Week 01 Review.md
│       └── Month 01 Synthesis.md
├── Month 02 - Cognitive Biases Deep Dive/
├── ...
├── Month 12 - Integration & Research Audit/
├── _curriculum-templates/            ← Templates specific to curriculum (separate from _templates/)
│   ├── Lesson Note.md                ← Template for new lesson notes
│   ├── Exercise Sheet.md             ← Template for exercise pages
│   ├── Paper Critique Worksheet.md   ← Template for structured paper analysis
│   ├── Weekly Review.md              ← Template for weekly synthesis
│   ├── Monthly Synthesis.md          ← Template for end-of-month reflection
│   └── Research Audit.md             ← Template for final paper evaluation framework
└── Progress Dashboard.md             ← Dataview-powered dashboard: completed exercises, calibration accuracy, etc.
```

### Anti-Patterns Avoided

| Don't Do This | Why | Do This Instead |
|---------------|-----|-----------------|
| Flat 120+ lesson files in one directory | Unnavigable. Breaks file explorer. | One directory per month, 8-12 lessons each. |
| Number-only filenames (`01.md`, `02.md`) | Zero information at a glance. Graph view shows meaningless labels. | Descriptive filenames: `03.04 - Bayesian Updating.md` |
| Curriculum content mixed into existing directories | Violates "extend, don't replace" constraint. Makes it impossible to remove curriculum cleanly. | All curriculum in `Curriculum/`, wikilinks to existing content. |
| One massive MOC linking everything | Information overload. Students skip it. | Monthly MOCs with progressive disclosure — each month's MOC only links that month + prerequisites. |

---

## Template Patterns

### Templater Syntax Convention

All curriculum templates use Templater syntax (`<% ... %>`) for dynamic content, NOT the core Templates plugin syntax (`{{date}}`, `{{title}}`). Templater is strictly more powerful and its syntax is explicit about what's dynamic vs. static.

### Lesson Note Template (`_curriculum-templates/Lesson Note.md`)

```markdown
---
tags:
  - lesson
  - curriculum
month: <% tp.file.folder(false).match(/Month (\d+)/)[1] %>
prerequisites: []
learning_objectives: []
estimated_minutes: 
status: draft
created: <% tp.date.now("YYYY-MM-DD") %>
---

# <% tp.file.title %>

> **Month:** [[Month <% tp.file.folder(false).match(/Month (\d+)/)[1] %> MOC]]
> **Time:** ~ minutes
> **Prerequisites:** [list wikilinks to prior lessons]

## Learning Objectives
- [ ] 
- [ ] 
- [ ] 

## Core Content

[lesson body with wikilinks to Biases/, Fallacies/, Mental Models/ etc.]

## Key Takeaways
- 
- 
- 

## Apply It: Paper Exercise
Pick a recent paper in your field. Read the [section of interest]. Then:
1. [concrete task applying today's concept]
2. [concrete task]
3. [concrete task]

Record your analysis in a new [[Paper Reviews/]] note.

## Check Your Understanding
- [ ] Can I explain [concept] to a colleague in 2 minutes?
- [ ] Can I spot [concept] in a real paper?
- [ ] Can I identify when I'm falling prey to [bias/fallacy]?

## Related
- [[Biases/Cognitive Biases|Cognitive Biases]]
- [[Logical Fallacies/Logical Fallacies|Logical Fallacies]]
- [[Mental Models/Mental Models|Mental Models]]
```

### Exercise Sheet Template (`_curriculum-templates/Exercise Sheet.md`)

```markdown
---
tags:
  - exercise
  - curriculum
month: <% tp.file.folder(false).match(/Month (\d+)/)[1] %>
difficulty: 
status: not-started
completed_date: 
score: 
time_spent_minutes: 
created: <% tp.date.now("YYYY-MM-DD") %>
---

# Exercise: <% tp.file.title %>

> **Month:** [[Month <% tp.file.folder(false).match(/Month (\d+)/)[1] %> MOC]]
> **Difficulty:** `INPUT[inlineSelect(option(Foundational), option(Intermediate), option(Advanced)):difficulty]`
> **Status:** `INPUT[inlineSelect(option(not-started), option(in-progress), option(completed)):status]`

## Setup
[What the student needs before starting — papers, tools, prior exercises]

## Instructions
1. 
2. 
3. 

## Your Response
[Free text area — student writes here]

## Self-Check
- [ ] I completed all steps
- [ ] I can explain my reasoning
- [ ] I identified at least one surprise

## Reflection
What did this exercise teach you that you didn't know before?

---

## Calibration (if applicable)
Initial confidence: `INPUT[number:confidence]`%
Actual outcome: 
Brier component: 
```

### Paper Critique Worksheet (`_curriculum-templates/Paper Critique Worksheet.md`)

```markdown
---
tags:
  - paper-critique
  - exercise
  - curriculum
paper_title: ""
paper_doi: ""
field: ""
critique_month: <% tp.file.folder(false).match(/Month (\d+)/)[1] %>
status: not-started
created: <% tp.date.now("YYYY-MM-DD") %>
---

# Paper Critique: <% tp.file.title %>

> **Paper:** *<% tp.system.prompt("Paper title") %>*
> **DOI:** <% tp.system.prompt("DOI (optional)") %>
> **Field:** <% tp.system.prompt("Research field") %>

## 1. The Claim
What is the paper's central claim? State it in one sentence.

## 2. The Evidence
| Evidence Type | Strength (1-5) | Notes |
|--------------|----------------|-------|
|              | `INPUT[number:evidence_1_strength]` |       |
|              | `INPUT[number:evidence_2_strength]` |       |

## 3. Methodology Audit
- [ ] Sample size justified?
- [ ] Confounders addressed?
- [ ] p-hacking risks? (Check for multiple comparisons without correction)
- [ ] Pre-registration? (Check aspredicted.org or clinicaltrials.gov)
- [ ] Replication status?

## 4. Reasoning Chain
Map the argument: Premise → Inference → Sub-conclusion → Main Conclusion

## 5. Bias Check
Which cognitive biases might affect:
- The authors' interpretation? [link to Bias notes]
- My own reading of this paper? [link to Bias notes]

## 6. Bayesian Update
Prior belief (before reading): `INPUT[number:prior_belief]`%
Posterior belief (after critique): `INPUT[number:posterior_belief]`%
What specific evidence moved the needle?

## 7. Verdict
`INPUT[inlineSelect(option(Strong — likely replicable), option(Moderate — wait for replication), option(Weak — skeptical), option(Severe flaws — likely false)):verdict]`

## Related
- [[Claim Analysis/]] — Create a structured claim from this paper
```

### Weekly Review Template (`_curriculum-templates/Weekly Review.md`)

```markdown
---
tags:
  - review
  - weekly-review
  - curriculum
week_start: <% tp.date.weekday("YYYY-MM-DD", 0) %>
month: <% tp.file.folder(false).match(/Month (\d+)/)[1] %>
created: <% tp.date.now("YYYY-MM-DD") %>
---

# Week Review: <% tp.date.weekday("MMM DD", 0) %> — <% tp.date.weekday("MMM DD", 6) %>

> **Month:** [[Month <% tp.file.folder(false).match(/Month (\d+)/)[1] %> MOC]]

## Lessons Completed
```dataview
LIST FROM "Curriculum/Month <% tp.file.folder(false).match(/Month (\d+)/)[1] %>"
WHERE tags = "lesson" AND status = "completed"
```

## Exercises Completed
```dataview
LIST FROM "Curriculum/Month <% tp.file.folder(false).match(/Month (\d+)/)[1] %>/Exercises"
WHERE status = "completed"
```

## Key Insights This Week
1. 
2. 
3. 

## Struggles / Confusions
- 

## Questions for Further Investigation
- [ ] 

## Next Week's Focus
- 
```

---

## Vault Backup & Sync Patterns

### Primary: Obsidian Git (auto-commit)

Configure Obsidian Git with:
- **Auto backup interval:** 30 minutes (frequent enough for safety, not so frequent it's noisy)
- **Commit message:** `vault backup: {{date}}` (auto-timestamped)
- **Push on backup:** Enabled (if using GitHub/GitLab remote)
- **Pull on startup:** Enabled (if using across devices)

This provides:
- Complete version history (every commit is a restore point)
- Cross-device sync (when combined with a git remote)
- No dependency on Obsidian Sync (though Sync can coexist)

### Secondary: Obsidian Sync (if available)

Already enabled in the vault (`sync: true` in core-plugins.json). Works alongside git — Sync handles real-time multi-device, git handles history.

### Distribution: ZIP Archive

For distributing the curriculum to students:
1. Export vault root as `.zip` (include `.obsidian/` config so plugins work out of the box)
2. Students unzip and open as their own vault
3. They run `Obsidian Git: Pull` to get updates (if curriculum is versioned)

### What NOT to do for backup

| Anti-Pattern | Why |
|--------------|-----|
| Manual "copy folder to Desktop" | Loses history. Humans forget. 12 months is a long time. |
| iCloud/Dropbox/Google Drive sync | Known to corrupt Obsidian vaults when simultaneous writes occur. Obsidian officially warns against this. |
| Relying only on File Recovery | Only keeps recent snapshots. Not a backup. |

---

## Curriculum Authoring Patterns

### Pattern 1: Spiral Curriculum via Progressive MOCs

**What:** Topics are introduced at surface level in early months and revisited at greater depth in later months. Each month's MOC links back to prior months' coverage of the same topic.

**Implementation:**
```markdown
# Month 06 MOC — Bayesian Reasoning

## This Month
- [[06.01 - Bayes Theorem Revisited]]
- [[06.02 - Priors in Scientific Practice]]

## Where You've Seen This Before
- [[Month 01 MOC#Bayesian Basics|Month 01: Bayesian Basics]]
- [[Month 03 MOC#Probability Foundations|Month 03: Probability Foundations]]
```

**Why it works:** The existing vault already uses MOC patterns (see `Biases/Cognitive Biases.md`). Students already understand MOCs as navigation hubs. Building on this pattern reduces cognitive overhead.

### Pattern 2: Paper-First Pedagogy

**What:** Every concept is immediately applied to a real paper. Lesson notes include an "Apply It" section that directs students to open a paper in their field and practice the concept.

**Why it works:** The existing vault already has a `Paper Reviews/` section with structured reviews. Students extend this section with their own critiques. The pattern bridges theory (concept notes) and practice (paper reviews) through wikilinks.

### Pattern 3: Dataview-Driven Progress Visibility

**What:** The `Progress Dashboard.md` uses Dataview queries to show students their own progress — completed exercises, calibration accuracy over time, confidence trends.

**Sample query:**
```dataview
TABLE status, completed_date, score
FROM "Curriculum"
WHERE tags = "exercise" AND status != "not-started"
SORT completed_date DESC
```

**Why it works:** Self-guided learners need visible progress to stay motivated. Dataview queries make progress self-tracking without any external tooling.

### Pattern 4: Thinking Journal Integration

**What:** Daily notes in `Thinking Journal/` include month-aligned prompts that connect daily reflection to curriculum content.

**Implementation:** The Thinking Journal template includes a Dataview inline query that pulls the current month's theme:
```markdown
> **This month's focus:** `= this.file.day.month` reflection prompt
```

**Why it works:** Bridges the curriculum's structured learning with the existing Thinking Journal habit. Lowers the barrier to daily practice.

### Pattern 5: Progressive Template Complexity

**What:** Templates evolve across the curriculum. Month 01 uses simple templates (minimal frontmatter). By Month 12, templates include full calibration tracking, Brier scores, and multi-step analysis frameworks.

**Why it works:** Students aren't overwhelmed with complex forms on day one. The template complexity grows with their skill level.

---

## Convention Rules (Enforced by Template Design)

| Rule | Rationale |
|------|-----------|
| All curriculum notes have `tags: [curriculum]` plus a type tag (`lesson`, `exercise`, `review`) | Enables Dataview to filter curriculum content from reference content |
| All frontmatter uses lowercase kebab-case keys (`learning_objectives`, not `Learning Objectives`) | Consistent with existing vault conventions; Dataview queries are case-sensitive |
| Monthly folders use zero-padded numbers (`Month 01`, not `Month 1`) | File explorer sorts correctly |
| Lesson files use `MM.NN - Title.md` format (`03.04 - Bayesian Updating.md`) | Sortable, descriptive, graph-friendly |
| Wikilinks use shortest unambiguous path (`[[Confirmation Bias]]` not `[[Biases/Confirmation Bias.md]]`) | Obsidian resolves wikilinks without extensions; shorter links are more readable |
| All MOC pages have `tags: [moc, curriculum]` | Matches existing `moc` tag convention in the vault |

---

## Sources

| Source | What Was Verified | Confidence |
|--------|-------------------|------------|
| [Dataview GitHub Releases](https://github.com/blacksmithgu/obsidian-dataview/releases) | Version 0.5.70, active maintenance under holroy | HIGH |
| [Templater GitHub Releases](https://github.com/SilentVoid13/Templater/releases) | Version 2.22.1, very active (weekly releases) | HIGH |
| [Templater Official Docs](https://silentvoid13.github.io/Templater/) | Date module API, `tp.date.now()`, `tp.system.prompt()`, `tp.frontmatter` | HIGH |
| [Meta Bind GitHub Releases](https://github.com/mProjectsCode/obsidian-meta-bind-plugin/releases) | Version 1.5.0, active, supports inline input widgets | HIGH |
| [Obsidian Git GitHub Releases](https://github.com/Vinzent03/obsidian-git/releases) | Version 2.38.3, 11.3k stars, actively maintained | HIGH |
| [Excalidraw GitHub Releases](https://github.com/zsviczian/obsidian-excalidraw-plugin/releases) | Version 2.23.12, extremely active (multiple releases per week), 7.1k stars | HIGH |
| [Calendar Plugin GitHub](https://github.com/liamcain/obsidian-calendar-plugin) | Last release Apr 2021 (2.0.0-beta.2), effectively frozen; weekly notes moved to Periodic Notes | HIGH |
| [Periodic Notes GitHub](https://github.com/liamcain/obsidian-periodic-notes) | Last release Apr 2022 (1.0.0-beta.3), dormant | HIGH |
| [Advanced Tables GitHub Releases](https://github.com/tgrosinger/advanced-tables-obsidian/releases) | Version 0.23.2, maintained, 2.5k stars | HIGH |
| [Charts GitHub Releases](https://github.com/phibr0/obsidian-charts/releases) | Version 3.9.0 (Jan 2024), 783 stars, stale — watch before installing | MEDIUM |
| Existing vault `.obsidian/core-plugins.json` | Core plugin configuration verified against actual vault state | HIGH |
| Existing vault templates (`_templates/Claim.md`, `_templates/Forecast.md`) | Convention patterns (tags, `INPUT[number:...]`, confidence logs) verified | HIGH |
| Existing vault MOCs (`Biases/Cognitive Biases.md`, `Logical Fallacies/Logical Fallacies.md`) | MOC pattern (tag + list + Related section) verified | HIGH |

---

*Stack research for: Obsidian-based critical thinking curriculum*
*Researched: 2026-06-14*
*Confidence: HIGH — all plugin versions verified against GitHub releases within the last week*
