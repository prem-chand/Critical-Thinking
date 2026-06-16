---
tags:
  - mental-models
  - cognitive-bias
---

# Cognitive Traps in Intelligence Analysis

**Source:** Richard Heuer, *The Psychology of Intelligence Analysis* (formerly classified CIA manual); via a video by Stephen Petro.

## Overview
Richard Heuer's framework identifies five cognitive traps that systematically degrade analytical quality. Originally developed for CIA analysts, these patterns appear in any domain requiring inference under uncertainty — including robotics research, system design, and engineering decisions.

---

## The Five Cognitive Traps

### 1. Mirror Imaging
**What it is:** Assuming others think, value, and prioritize the same things you do.

**Real-world failure:** CIA missed India's 1998 nuclear tests by projecting economic cost-benefit logic onto a government driven by national pride and sovereignty.

**Counter-technique:**
> Write "If I were them, I would..." — then cross it out.
> Focus instead on *their* actual constraints, incentives, and values from evidence.

---

### 2. Satisficing
**What it is:** Locking onto the first plausible hypothesis and collecting only confirming evidence, rather than disconfirming it.

**Real-world failure:** CIA failed to predict the Iranian Revolution by anchoring on a stable-Shah hypothesis.

**Counter-technique:**
> Ask: *"What evidence would cause me to change my mind?"*
> If you can't answer this, you're satisficing.

---

### 3. Analysis of Competing Hypotheses (ACH)
**What it is:** A structured method to *counter* satisficing — the only trap here that is a solution framework, not a failure mode.

**Method:**
1. List all plausible hypotheses
2. Build a matrix: hypotheses as columns, evidence as rows
3. Mark each cell: consistent, inconsistent, or irrelevant
4. Eliminate hypotheses with strong disconfirming evidence
5. Prefer the hypothesis with the *fewest inconsistencies*, not the most confirmations

**Key insight:** The goal is elimination, not confirmation.

---

### 4. The Vividness Criterion
**What it is:** Letting dramatic, anecdotal, or emotionally salient information override base-rate statistical evidence.

**Real-world failure:** Misinterpretations during the Vietnam War driven by vivid battlefield anecdotes over aggregate data.

**Counter-technique:**
> Ask: *"What is the base rate?"*
> Ask: *"Is this anecdote representative, or an outlier?"*
> Weight abstract statistics over vivid stories deliberately.

---

### 5. The Information Paradox
**What it is:** More information increases *confidence* in a judgment without necessarily increasing *accuracy* — often producing dangerous overconfidence.

**Counter-technique:**
> Before gathering more data, ask: *"Do I already have the minimum information needed to decide?"*
> If yes — stop collecting, and instead challenge your **interpretive framework**.

---

## Connecting Threads
| Trap | Core Error | Fix |
|---|---|---|
| Mirror Imaging | Projecting self onto others | Use their evidence, not your logic |
| Satisficing | Confirming one hypothesis | Seek disconfirming evidence |
| (ACH) | *(Solution framework)* | Elimination matrix |
| Vividness Criterion | Story > statistics | Ask for base rates |
| Information Paradox | More data = more confident | Challenge framework, not data volume |

---

## Personal Notes / Applications
- In **sim-to-real transfer**: satisficing shows up when we confirm a policy works in sim without aggressively testing failure modes in the real domain
- Mirror imaging in **system design**: assuming users/robots will behave the way we model them to behave
- Information paradox in **hyperparameter tuning**: running more experiments without questioning the training objective itself

---

## Related
- [[Mental Models/Mental Models|Mental Models]]
- [[Critical Thinking]]
- [[Biases/Cognitive Biases|Cognitive Biases]]

### Traps mapped to individual biases
- **Satisficing** → [[Biases/Confirmation Bias|Confirmation Bias]], [[Biases/Anchoring Bias|Anchoring Bias]]
- **Vividness Criterion** → [[Biases/Availability Bias|Availability Bias]]
- **Information Paradox** → [[Biases/Overconfidence|Overconfidence]]
- **ACH** counters all of the above — see also [[Mental Models/Systems Thinking|Systems Thinking]] and [[Forecasts/Forecasts|Forecasts]] (base-rate / calibration practice)