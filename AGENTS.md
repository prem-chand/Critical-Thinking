# AGENTS.md

## This is an Obsidian vault, NOT a code project
There are no build steps, tests, linters, or code. Do not run commands that assume a codebase.

## Vault structure
```
Critical Thinking.md          ← root hub / Map of Content (MOC)
Biases/                       ← one note per bias + MOC (Cognitive Biases.md)
Books/                        ← book notes with author/year frontmatter
Claim Analysis/               ← structured claims using _templates/Claim.md
Forecasts/                    ← predictions + AI/ and Robotics/ subdirs
Logical Fallacies/            ← one note per fallacy + MOC
Mental Models/                ← one note per model + MOC
Paper Reviews/                ← academic paper reviews
Thinking Journal/             ← daily reflections
_templates/                   ← Claim.md and Forecast.md templates
```

## Conventions

### Frontmatter (YAML, `---` delimited)
- Every page must have a `tags:` list.
- Hub/index pages use tag `moc` plus a content-type tag.
- Content notes use the content-type tag (e.g., `cognitive-bias`, `claim`, `book`, `mental-models`, `forecast`).
- Book notes add `author` and `year` fields.
- Claim notes add `confidence` (integer %), `source` (string), `date`.
- Forecast notes add `confidence`, `status`, `review_date`, `resolution_date`, `outcome`, `brier_score`.

### Links
- Internal links use `[[wikilink]]` syntax (Obsidian default).
- When linking across directories, include the path: `[[Biases/Cognitive Biases]]`.
- Using a pipe for display text: `[[Biases/Cognitive Biases|Cognitive Biases]]`.

### MOC pattern
Each section has an index file that:
- Lists all entries in that section with wikilinks
- Links back to the root `Critical Thinking.md` hub
- Links to related sections

### Adding new content
- **New bias/falseacy/mental model**: Create in the appropriate directory, add it to the section MOC list.
- **New claim**: Use `_templates/Claim.md` as a starting point.
- **New forecast**: Use `_templates/Forecast.md` as a starting point.
- **New book note**: Include `author` and `year` in frontmatter; link from the `Critical Thinking.md` books section if appropriate.
- After adding any new file, update the parent MOC to include a link to it.

### File naming
- Title Case for all note files (e.g., `Confirmation Bias.md`, `First Principles Thinking.md`).
- Dashes are allowed as needed (e.g., `Dunning-Kruger Effect.md`).

### Obsidian plugins active
Daily notes, templates, properties, tags, backlinks, graph, and canvas are enabled. Zettelkasten prefixer is disabled (no ID prefixes on filenames). Sync is enabled.

<!-- GSD:project-start source:PROJECT.md -->
## Project

**Critical Thinking for Researchers — 12-Month Curriculum**

A 12-month structured curriculum that teaches researchers critical thinking through an integrated lens of philosophy, logic, probability, statistics, scientific reasoning, and paper critique. The entire curriculum lives as a single Obsidian knowledge graph — a web of interlinked notes, exercises, templates, and structured claims that students build and inhabit throughout the year. Built atop the existing Critical Thinking vault, extending its Biases, Fallacies, Mental Models, and Claim Analysis sections with progressive learning materials.

**Core Value:** Transform a researcher's relationship with their own thinking — from passive consumer of papers and producer of analyses to a self-calibrating reasoner who explicitly tracks beliefs, quantifies uncertainty, and catches their own cognitive errors before they become published mistakes.

### Constraints

- **Platform:** Obsidian-only. No external tooling, web apps, or databases.
- **Format:** Markdown notes with YAML frontmatter, wikilinks, and Obsidian-flavored syntax.
- **Duration:** Must be completable in 12 months at 3-5 hours/week.
- **Existing vault:** Must not break or restructure the existing vault — curriculum content extends it in a self-contained subdirectory.
- **Plugins:** Dataview and Charts are available for dashboards; no assumption beyond core plugins.
<!-- GSD:project-end -->

<!-- GSD:stack-start source:research/STACK.md -->
## Technology Stack

## Executive Summary
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
## Folder Structure Convention
### Curriculum Extends, Doesn't Replace
### Anti-Patterns Avoided
| Don't Do This | Why | Do This Instead |
|---------------|-----|-----------------|
| Flat 120+ lesson files in one directory | Unnavigable. Breaks file explorer. | One directory per month, 8-12 lessons each. |
| Number-only filenames (`01.md`, `02.md`) | Zero information at a glance. Graph view shows meaningless labels. | Descriptive filenames: `03.04 - Bayesian Updating.md` |
| Curriculum content mixed into existing directories | Violates "extend, don't replace" constraint. Makes it impossible to remove curriculum cleanly. | All curriculum in `Curriculum/`, wikilinks to existing content. |
| One massive MOC linking everything | Information overload. Students skip it. | Monthly MOCs with progressive disclosure — each month's MOC only links that month + prerequisites. |
## Template Patterns
### Templater Syntax Convention
### Lesson Note Template (`_curriculum-templates/Lesson Note.md`)
# <% tp.file.title %>
## Learning Objectives
- [ ] 
- [ ] 
- [ ] 
## Core Content
## Key Takeaways
- 
- 
- 
## Apply It: Paper Exercise
## Check Your Understanding
- [ ] Can I explain [concept] to a colleague in 2 minutes?
- [ ] Can I spot [concept] in a real paper?
- [ ] Can I identify when I'm falling prey to [bias/fallacy]?
## Related
- [[Biases/Cognitive Biases|Cognitive Biases]]
- [[Logical Fallacies/Logical Fallacies|Logical Fallacies]]
- [[Mental Models/Mental Models|Mental Models]]
### Exercise Sheet Template (`_curriculum-templates/Exercise Sheet.md`)
# Exercise: <% tp.file.title %>
## Setup
## Instructions
## Your Response
## Self-Check
- [ ] I completed all steps
- [ ] I can explain my reasoning
- [ ] I identified at least one surprise
## Reflection
## Calibration (if applicable)
### Paper Critique Worksheet (`_curriculum-templates/Paper Critique Worksheet.md`)
# Paper Critique: <% tp.file.title %>
## 1. The Claim
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
## 5. Bias Check
- The authors' interpretation? [link to Bias notes]
- My own reading of this paper? [link to Bias notes]
## 6. Bayesian Update
## 7. Verdict
## Related
- [[Claim Analysis/]] — Create a structured claim from this paper
### Weekly Review Template (`_curriculum-templates/Weekly Review.md`)
# Week Review: <% tp.date.weekday("MMM DD", 0) %> — <% tp.date.weekday("MMM DD", 6) %>
## Lessons Completed
## Exercises Completed
## Key Insights This Week
## Struggles / Confusions
- 
## Questions for Further Investigation
- [ ] 
## Next Week's Focus
- 
## Vault Backup & Sync Patterns
### Primary: Obsidian Git (auto-commit)
- **Auto backup interval:** 30 minutes (frequent enough for safety, not so frequent it's noisy)
- **Commit message:** `vault backup: {{date}}` (auto-timestamped)
- **Push on backup:** Enabled (if using GitHub/GitLab remote)
- **Pull on startup:** Enabled (if using across devices)
- Complete version history (every commit is a restore point)
- Cross-device sync (when combined with a git remote)
- No dependency on Obsidian Sync (though Sync can coexist)
### Secondary: Obsidian Sync (if available)
### Distribution: ZIP Archive
### What NOT to do for backup
| Anti-Pattern | Why |
|--------------|-----|
| Manual "copy folder to Desktop" | Loses history. Humans forget. 12 months is a long time. |
| iCloud/Dropbox/Google Drive sync | Known to corrupt Obsidian vaults when simultaneous writes occur. Obsidian officially warns against this. |
| Relying only on File Recovery | Only keeps recent snapshots. Not a backup. |
## Curriculum Authoring Patterns
### Pattern 1: Spiral Curriculum via Progressive MOCs
# Month 06 MOC — Bayesian Reasoning
## This Month
- [[06.01 - Bayes Theorem Revisited]]
- [[06.02 - Priors in Scientific Practice]]
## Where You've Seen This Before
- [[Month 01 MOC#Bayesian Basics|Month 01: Bayesian Basics]]
- [[Month 03 MOC#Probability Foundations|Month 03: Probability Foundations]]
### Pattern 2: Paper-First Pedagogy
### Pattern 3: Dataview-Driven Progress Visibility
### Pattern 4: Thinking Journal Integration
### Pattern 5: Progressive Template Complexity
## Convention Rules (Enforced by Template Design)
| Rule | Rationale |
|------|-----------|
| All curriculum notes have `tags: [curriculum]` plus a type tag (`lesson`, `exercise`, `review`) | Enables Dataview to filter curriculum content from reference content |
| All frontmatter uses lowercase kebab-case keys (`learning_objectives`, not `Learning Objectives`) | Consistent with existing vault conventions; Dataview queries are case-sensitive |
| Monthly folders use zero-padded numbers (`Month 01`, not `Month 1`) | File explorer sorts correctly |
| Lesson files use `MM.NN - Title.md` format (`03.04 - Bayesian Updating.md`) | Sortable, descriptive, graph-friendly |
| Wikilinks use shortest unambiguous path (`[[Confirmation Bias]]` not `[[Biases/Confirmation Bias.md]]`) | Obsidian resolves wikilinks without extensions; shorter links are more readable |
| All MOC pages have `tags: [moc, curriculum]` | Matches existing `moc` tag convention in the vault |
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
<!-- GSD:stack-end -->

<!-- GSD:conventions-start source:CONVENTIONS.md -->
## Conventions

Conventions not yet established. Will populate as patterns emerge during development.
<!-- GSD:conventions-end -->

<!-- GSD:architecture-start source:ARCHITECTURE.md -->
## Architecture

Architecture not yet mapped. Follow existing patterns found in the codebase.
<!-- GSD:architecture-end -->

<!-- GSD:skills-start source:skills/ -->
## Project Skills

No project skills found. Add skills to any of: `.claude/skills/`, `.agents/skills/`, `.cursor/skills/`, `.github/skills/`, or `.codex/skills/` with a `SKILL.md` index file.
<!-- GSD:skills-end -->

<!-- GSD:workflow-start source:GSD defaults -->
## GSD Workflow Enforcement

Before using Edit, Write, or other file-changing tools, start work through a GSD command so planning artifacts and execution context stay in sync.

Use these entry points:
- `/gsd-quick` for small fixes, doc updates, and ad-hoc tasks
- `/gsd-debug` for investigation and bug fixing
- `/gsd-execute-phase` for planned phase work

Do not make direct repo edits outside a GSD workflow unless the user explicitly asks to bypass it.
<!-- GSD:workflow-end -->

<!-- GSD:profile-start -->
## Developer Profile

> Profile not yet configured. Run `/gsd-profile-user` to generate your developer profile.
> This section is managed by `generate-claude-profile` -- do not edit manually.
<!-- GSD:profile-end -->
