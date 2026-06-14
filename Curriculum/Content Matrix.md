---
tags:
  - curriculum
  - reference
---

# Content Matrix

The curriculum spans **6 disciplines** across **12 months** with **4 depth levels**:

| Depth | Label | Description |
|-------|-------|-------------|
| 1 | Foundation | Core concepts, vocabulary, recognition |
| 2 | Working Knowledge | Application, basic tool use |
| 3 | Analytical | Decomposition, critique, evaluation |
| 4 | Synthesis | Integration, creation, original analysis |

## Discipline × Month Matrix

| Month | Philosophy / Logic | Formal Logic | Probability | Statistics | Scientific Reasoning | Paper Analysis |
|-------|-------------------|--------------|-------------|------------|---------------------|----------------|
| M01 | 1: Truth, belief, knowledge | 1: Arguments, premises, conclusions | 1: Uncertainty, basic probability | 1: Descriptive stats overview | 1: Scientific method, hypothesis formation | 1: Paper anatomy, reading strategies |
| M02 | 1: Epistemology, justification | 1: Deductive reasoning, syllogisms | 1: Probability rules, conditional prob. | 1: Sampling, distributions | 1: Operationalization, measurement | 1: Structured reading, annotation |
| M03 | 2: Cognitive bias taxonomy | 1: Inductive reasoning, analogies | 2: Heuristics & biases in probability | 2: Statistical fallacies, Simpson's paradox | 2: Experimental design basics | 2: Identifying bias in published papers |
| M04 | 2: Bayesian epistemology | 2: Bayesian reasoning as logic | 3: Bayes' theorem, priors, posteriors | 2: Bayesian vs frequentist | 2: Evidential reasoning | 2: Bayesian critique of claims |
| M05 | 2: Philosophy of probability | 2: Statistical syllogisms | 2: Probability distributions | 3: Hypothesis testing, p-values | 3: NHST critique, replication | 3: Interpreting statistical claims |
| M06 | 3: Causation & correlation | 2: Counterfactual reasoning | 3: Causal Bayesian networks | 3: Causal inference, DAGs | 3: Causal claims in research | 3: Evaluating causal claims |
| M07 | 3: Popper, Kuhn, Lakatos | 3: Falsification logic | 3: Evidential probability | 3: Meta-analysis, effect sizes | 4: Reproducibility, ethics | 4: Methodology audit |
| M08 | 3: Argumentation theory | 3: Complex argument structures | 2: Probability in argumentation | 2: Data viz literacy | 3: Communicating uncertainty | 4: Structured critique writing |
| M09 | 3: Epistemic humility | 3: Prediction logic | 4: Calibration, scoring rules | 4: Time series, prediction markets | 4: Replication crisis deep dive | 4: Pre-registration, registered reports |
| M10 | 4: Integrated epistemology | 3: Multi-modal reasoning | 4: Probabilistic reasoning integration | 4: Integrated statistical toolkit | 4: Research workflow design | 4: Comprehensive paper audit |
| M11 | 4: Metacognition, intellectual virtues | 4: Advanced formal methods | 4: Advanced probability models | 4: Advanced statistical methods | 4: Peer review simulation | 4: Full paper deconstruction |
| M12 | 4: Personal epistemology | 4: Master-level reasoning | 4: Probabilistic mastery | 4: Statistical mastery | 4: Research program design | 4: Independent paper audit |

## Frontmatter Schema

Every curriculum lesson note must include these frontmatter fields:

| Key | Type | Required | Values | Description |
|-----|------|----------|--------|-------------|
| `tags` | list | yes | `[curriculum, lesson]` | Type classification |
| `month` | int | yes | `1` – `12` | Month number |
| `week` | int | yes | `1` – `4` | Week within the month |
| `thread` | string | yes | `philosophy-logic`, `formal-logic`, `probability`, `statistics`, `scientific-reasoning`, `paper-analysis` | Which discipline thread |
| `discipline` | string | yes | `philosophy-logic`, `formal-logic`, `probability`, `statistics`, `scientific-reasoning`, `paper-analysis` | Same as thread (cross-reference use) |
| `depth-level` | int | yes | `1` – `4` | Depth according to the matrix above |
| `core` | bool | yes | `true`, `false` | Whether this is a core (required) lesson |

### Example Frontmatter

```yaml
---
tags:
  - curriculum
  - lesson
month: 4
week: 2
thread: probability
discipline: probability
depth-level: 3
core: true
---
```

## Dataview Query Examples

### Show all core lessons for Month 04

```dataview
TABLE month, week, discipline, depth-level
FROM "Curriculum"
WHERE month = 4 AND core = true
SORT week ASC
```

### Show all lessons at depth-level 4

```dataview
TABLE month, week, thread, core
FROM "Curriculum"
WHERE depth-level = 4
SORT month ASC, week ASC
```

### Count lessons per discipline per month

```dataview
TABLE rows.file.link
FROM "Curriculum"
WHERE discipline
FLATTEN discipline
GROUP BY discipline + " / Month " + month
```

## Related

- [[Curriculum/Curriculum Hub|Curriculum Hub]]
- [[Curriculum/12-Month Outcomes|12-Month Outcomes]]
- [[Curriculum/Thread MOCs/Epistemology Thread|Epistemology Thread]]
- [[Curriculum/Thread MOCs/Logic Thread|Logic Thread]]
- [[Curriculum/Thread MOCs/Probability Thread|Probability Thread]]
- [[Curriculum/Thread MOCs/Statistics Thread|Statistics Thread]]
- [[Curriculum/Thread MOCs/Scientific Method Thread|Scientific Method Thread]]
- [[Curriculum/Thread MOCs/Paper Critique Thread|Paper Critique Thread]]
