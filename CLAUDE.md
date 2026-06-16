# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

An **Obsidian vault** on critical thinking — a personal knowledge base, not a software project. There is no code, build, lint, or test step. Do not run package managers, test runners, or anything that assumes a codebase. "Working" here means editing Markdown notes, maintaining wikilinks, and keeping index pages in sync.

`AGENTS.md` is the canonical, detailed convention reference (frontmatter schemas, link syntax, file naming, active Obsidian plugins). Read it before editing. The notes below cover the structure and the rules that are easy to get wrong.

## Structure

The vault lives under `content/` (the repo root holds only meta/tooling: this file, `AGENTS.md`, `.claude/`, and Quartz publishing config). **All note paths below are relative to `content/`** — when editing, prefix them accordingly (e.g. `content/Biases/Cognitive Biases.md`). This layout exists so the static-site generator (Quartz) publishes `content/` while keeping meta files out of the public site; open the Obsidian vault on the `content/` folder.

The vault is a hub-and-spoke graph. `Critical Thinking.md` (the `content/` root) is the top-level Map of Content (MOC) linking out to each section. Every section directory has its own MOC index file (e.g. `Biases/Cognitive Biases.md`, `Logical Fallacies/Logical Fallacies.md`) that lists its entries and links back to the root hub.

Sections (under `content/`): `Biases/`, `Logical Fallacies/`, `Mental Models/` (one note per concept + a MOC), `Claim Analysis/` and `Forecasts/` (instances of structured templates; Forecasts has `AI/` and `Robotics/` sub-MOCs), `Books/` (notes with `author`/`year`), `Paper Reviews/`, `Thinking Journal/`. Templates live in `_templates/`.

## The rules most likely to bite

- **Update the parent MOC whenever you add a note.** A new note is only "added" once its section MOC links to it — otherwise it's orphaned in the graph. This is the single most common omission.
- **Frontmatter is mandatory.** Every page needs a `tags:` list with the correct content-type tag (`cognitive-bias`, `logical-fallacy`, `mental-models`, `claim`, `forecast`, `book`, ...). MOC pages additionally carry `moc`. Template-derived notes (claims, forecasts) have extra typed fields — copy the schema from `_templates/` and `AGENTS.md`, don't invent fields.
- **Links use Obsidian `[[wikilink]]` syntax**, not Markdown links. Cross-directory links include the path: `[[Biases/Cognitive Biases]]`; pipe for display text: `[[Biases/Cognitive Biases|Cognitive Biases]]`. Wikilinks resolve by note title, so renaming a file silently breaks inbound links — grep for the old title and fix references.
- **New claims and forecasts start from `_templates/Claim.md` / `_templates/Forecast.md`.** Preserve the section headings and the Confidence Log table; these encode the calibration-tracking workflow (confidence %, base rates, what would update the belief, Brier scores).
- **File naming is Title Case** (`First Principles Thinking.md`), dashes allowed where natural (`Dunning-Kruger Effect.md`). No Zettelkasten ID prefixes.

## Git note

`content/.obsidian/workspace.json` changes on nearly every Obsidian launch (UI layout state) — it's noise, don't bundle it into content commits. A `.planning/` directory and several `Curriculum/` files appear deleted in the working tree; treat the current files on disk as the source of truth and don't resurrect removed content unless asked.

## Publishing

The vault publishes online via **Quartz 5** (static-site generator) from the `content/` directory, deployed to GitHub Pages at **https://thinking.probabilize.dev** on every push to `master`. Anything outside `content/` is not published. The notes are intended to be public — but stay mindful that edits here become a live, indexable website.

**Quartz cannot render Obsidian-only plugins.** This is the easiest way to make content silently break on the live site:

- **Dataview** (` ```dataview ` blocks) and **Meta Bind** (`INPUT[...]`, `VIEW[...]`) do not run — they render as raw code/text. So MOCs must list their children with **static `[[wikilinks]]`**, not Dataview queries. The `_templates/` notes use these dynamic features for the in-Obsidian calibration workflow, which is why `_templates/` is excluded from publishing (`ignorePatterns` in `quartz.config.yaml`).
- This reinforces the top rule: when you add a claim/forecast/journal entry, add a static wikilink to its section MOC. The dynamic dashboards only work inside Obsidian.
- The site homepage is `content/index.md` (titled "Critical Thinking", alias `Critical Thinking` so `[[Critical Thinking]]` backlinks resolve). Quartz serves it at `/`; don't rename it.
- Build/preview locally with `npx quartz build --serve`; plugins are fetched via `npx quartz plugin install` (NOT `npm run install-plugins`, which is broken). Quartz framework files live at the repo root and are committed.
