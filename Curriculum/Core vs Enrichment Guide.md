---
tags:
  - curriculum
  - reference
---

# Core vs Enrichment Guide

## The 70/30 Rule

Core lessons (~70% of content) are **required** — they form the prerequisite chain that enables the Month 12 capstone. Enrichment lessons (~30%) are **optional deep-dives** — valuable extensions that can be safely skipped without breaking the sequence.

- **Core** lessons tagged `#core` in monthly MOCs and have `core: true` in frontmatter
- **Enrichment** lessons tagged `#enrichment` in monthly MOCs and have `core: false` in frontmatter

## Per-Month Breakdown

| Month | Core | Enrichment | Total | Rationale for Core |
|-------|------|------------|-------|--------------------|
| M01 | 8 | 2 | 10 | Foundation: argument basics, paper anatomy, uncertainty intro |
| M02 | 8 | 2 | 10 | Epistemology, deduction, probability rules — all prerequisites |
| M03 | 6 | 4 | 10 | Bias taxonomy and experimental design are core; some bias deep-dives are enrichment |
| M04 | 8 | 2 | 10 | Bayesian reasoning is the curriculum's spine — all core |
| M05 | 6 | 4 | 10 | NHST critique is core; advanced distribution theory is enrichment |
| M06 | 6 | 4 | 10 | Causal inference is core; advanced DAG construction is enrichment |
| M07 | 8 | 2 | 10 | Falsification, meta-analysis, reproducibility — capstone prerequisites |
| M08 | 6 | 4 | 10 | Argumentation and critique writing are core; viz literacy extras are enrichment |
| M09 | 6 | 4 | 10 | Calibration and prediction are core; time series deep-dives are enrichment |
| M10 | 10 | 0 | 10 | Peak milestone — all content is core (compressed, high-stakes month) |
| M11 | 4 | 2 | 6 | Valley — core is the gap-filling menu; enrichment is optional stretch topics |
| M12 | 6 | 0 | 6 | Capstone — all content is core (final audit preparation and execution) |
| **Total** | **82** | **28** | **110** | **~75% core, ~25% enrichment** |

## Skip Strategy

If you fall behind:

1. **Always complete Core lessons.** They form the prerequisite chain for later months.
2. **Skip Enrichment without guilt.** These are optional explorations, not required knowledge.
3. **Use Month 11's Gap Menu** to fill any Core gaps you skipped. The Gap Menu is your catch-up mechanism.
4. **Never skip a whole month.** If pressed for time, do the Core 60-70% and move on.

## Dataview Query: Core Lessons This Month

```dataview
TABLE week, discipline, depth-level
FROM "Curriculum"
WHERE month = this.month AND core = true
SORT week ASC
```

## Related

- [[Curriculum/Content Matrix|Content Matrix]]
- [[Curriculum/Monthly MOCs|Monthly MOCs]]
- [[Curriculum/Curriculum Hub|Curriculum Hub]]
