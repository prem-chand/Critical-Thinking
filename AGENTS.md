# AGENTS.md

## This is an Obsidian vault, NOT a code project
There are no build steps, tests, linters, or code. Do not run commands that assume a codebase.

## Vault structure
The vault lives under `content/`; the repo root holds only meta/tooling (`AGENTS.md`, `CLAUDE.md`, `.claude/`, Quartz config). Open the Obsidian vault on the `content/` folder. Paths below are relative to `content/`, and the vault publishes online via Quartz from this directory.
```
content/
  Critical Thinking.md        ← root hub / Map of Content (MOC)
  Biases/                     ← one note per bias + MOC (Cognitive Biases.md)
  Books/                      ← book notes with author/year frontmatter
  Claim Analysis/             ← structured claims using _templates/Claim.md
  Forecasts/                  ← predictions + AI/ and Robotics/ subdirs
  Logical Fallacies/          ← one note per fallacy + MOC
  Mental Models/              ← one note per model + MOC
  Paper Reviews/              ← academic paper reviews
  Thinking Journal/           ← daily reflections
  _templates/                 ← Claim.md and Forecast.md templates
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
- **New bias/fallacy/mental model**: Create in the appropriate directory, add it to the section MOC list.
- **New claim**: Use `_templates/Claim.md` as a starting point.
- **New forecast**: Use `_templates/Forecast.md` as a starting point.
- **New book note**: Include `author` and `year` in frontmatter; link from the `Critical Thinking.md` books section if appropriate.
- After adding any new file, update the parent MOC to include a link to it.

### File naming
- Title Case for all note files (e.g., `Confirmation Bias.md`, `First Principles Thinking.md`).
- Dashes are allowed as needed (e.g., `Dunning-Kruger Effect.md`).

### Obsidian plugins active
Daily notes, templates, properties, tags, backlinks, graph, and canvas are enabled. Zettelkasten prefixer is disabled (no ID prefixes on filenames). Sync is enabled.
