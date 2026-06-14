---
tags:
  - curriculum
  - diagnostic
status: active
---

# Month 00 Entry Diagnostic

This is a **self-diagnostic**, not a test. There are no wrong answers in the sense that this is about establishing where **you** are starting from. You will revisit these questions in Month 12 to measure growth.

For each question, choose your answer, then reveal the suggested answer to calibrate your understanding. Use the confidence sliders to record how sure you feel about your answer — this is the most important data point in the diagnostic.

---

## Thread 1: Logic & Reasoning

### Q1
Which of the following is **not** a necessary condition for an argument?

- A. A claim that something is true
- B. A premise that provides support for a conclusion
- C. At least two premises
- D. A conclusion that is claimed to follow from premises

> [!note]- Reveal Answer
> **C.** An argument can have a single premise supporting a conclusion. Two premises are not necessary.

### Q2
"All humans are mortal. Socrates is human. Therefore, Socrates is mortal." This is an example of:

- A. Inductive reasoning
- B. Deductive reasoning
- C. Abductive reasoning
- D. Analogical reasoning

> [!note]- Reveal Answer
> **B.** The conclusion follows necessarily from the premises — the hallmark of deduction.

### Q3
If it rains, the ground will be wet. The ground is wet. Therefore, it rained. Identify the fallacy.

- A. Denying the antecedent
- B. Affirming the consequent
- C. Begging the question
- D. False dichotomy

> [!note]- Reveal Answer
> **B.** Affirming the consequent. Wet ground could have other causes (sprinklers, spilled water).

### Q4
**Scenario:** A defendant is accused of theft. The prosecutor argues: "If the defendant is innocent, he would not have been at the crime scene. But he was at the crime scene. Therefore, he is guilty."
How confident are you that this argument is valid?

`INPUT[number:q4_confidence]`%

> [!note]- Reveal Answer
> **Not valid.** This is affirming the consequent. Being at the crime scene does not prove guilt — an innocent person can be present. The argument confuses necessary and sufficient conditions.

### Q5
Identify the most serious problem with this analogy: "Banning violent video games is like banning books — both are forms of censorship that violate free expression."

- A. Video games are interactive, books are not
- B. The analogy ignores the difference in harm between the two
- C. Both A and B are relevant disanalogies
- D. The analogy is actually sound

> [!note]- Reveal Answer
> **C.** Both disanalogies are relevant: video games' interactivity and the differential concerns about harm make the analogy weak.

---

## Thread 2: Probability & Statistics

### Q6
A test for a disease is 99% accurate (99% sensitivity, 99% specificity). The disease affects 1 in 10,000 people. You test positive. What is the approximate probability you actually have the disease?

- A. 99%
- B. 50%
- C. About 1%
- D. 0.1%

> [!note]- Reveal Answer
> **C. About 1%.** Use Bayes' theorem. Out of 10,000 people: 1 has the disease (likely detected), 9,999 don't, 99 of whom get false positives. So ~1% positive predictive value. This is the classic base-rate fallacy.

### Q7
A fair coin is flipped 5 times and lands heads each time. What is the probability it lands heads on the 6th flip?

- A. Less than 50% (law of averages)
- B. Exactly 50%
- C. More than 50% (it's on a streak)
- D. Depends on the coin

Your confidence in this answer:

`INPUT[number:q7_confidence]`%

> [!note]- Reveal Answer
> **B. Exactly 50%.** Coins have no memory. The gambler's fallacy is believing past outcomes affect independent future ones.

### Q8
Which of these describes p < 0.05?

- A. There is a 5% chance the null hypothesis is true
- B. There is a 95% chance the alternative hypothesis is true
- C. If the null hypothesis were true, you would see data this extreme less than 5% of the time
- D. The probability of making a Type II error is 5%

> [!note]- Reveal Answer
> **C.** The p-value is P(data or more extreme | null hypothesis). It is **not** the probability the null hypothesis is true (a common misinterpretation).

### Q9
**Scenario:** You read that a correlation of r = 0.3 exists between meditation and life satisfaction (p < 0.001, N = 5000). Which interpretation is most warranted?

- A. Meditation causes increased life satisfaction
- B. The effect is small but unlikely to be due to chance
- C. The effect is large because p is very small
- D. The result is meaningless because r is small

> [!note]- Reveal Answer
> **B.** With N=5000, even small correlations reach significance. r=0.3 is modest. Very small p does not mean large effect — it means precise estimate.

### Q10
If you run 20 independent statistical tests and use α = 0.05 for each, what is the probability of at least one false positive?

- A. 0.05
- B. ~0.36 (1 - 0.95²⁰)
- C. ~0.64
- D. 1.0

> [!note]- Reveal Answer
> **C. ~0.64.** 1 - (0.95)²⁰ ≈ 0.64. This is the multiple comparisons problem. Correction methods (Bonferroni, FDR) exist for this reason.

---

## Thread 3: Scientific Reasoning

### Q11
Which of the following best characterizes falsification in science?

- A. A theory is scientific if it can be proven true
- B. A theory is scientific if it can, in principle, be shown false by evidence
- C. A theory is scientific if most experts agree with it
- D. A theory is scientific if it has been replicated

> [!note]- Reveal Answer
> **B.** Falsifiability (Popper) is the criterion that a scientific claim must be testable and potentially disprovable.

### Q12
A study finds that ice cream sales and drowning deaths are correlated (r = 0.8). What is the most likely explanation?

- A. Ice cream consumption causes drowning
- B. Drowning causes people to buy ice cream
- C. A third variable (temperature/summer) drives both
- D. The correlation is coincidental

> [!note]- Reveal Answer
> **C.** Confounding variable: hot weather increases both ice cream sales and swimming (hence drowning risk). Correlation ≠ causation.

### Q13
Which of these practices most reduces the risk of p-hacking?

- A. Collecting data until p < 0.05
- B. Pre-registering the analysis plan before data collection
- C. Reporting only significant results
- D. Running multiple analyses and picking the best one

> [!note]- Reveal Answer
> **B.** Pre-registration locks in the analysis plan, preventing researchers from exploiting researcher degrees of freedom.

### Q14
**Scenario:** A replication study of a famous psychology finding fails to replicate (p = 0.40). The original authors argue the replication was not exact. Who bears the burden of proof?

- A. The original authors — the failure to replicate weakens the claim
- B. The replicators — their method was different
- C. Neither — the result is inconclusive
- D. Both — science will sort it out over time

Your confidence:

`INPUT[number:q14_confidence]`%

> [!note]- Reveal Answer
> **A.** While exact replications are ideal, when many close replications fail, the original claim should be downgraded. The burden shifts to the original authors to show why their specific method was essential.

### Q15
Which is the strongest evidence for a causal claim?

- A. A meta-analysis of 10 randomized controlled trials
- B. A single large observational study
- C. An expert opinion from a Nobel laureate
- D. A mechanism proposed in a theoretical paper

> [!note]- Reveal Answer
> **A.** Meta-analyses of RCTs sit at the top of the evidence hierarchy. Expert opinion is the weakest despite its surface appeal.

---

## Thread 4: Metacognition & Calibration

### Q16
When you are 90% confident in an answer, about how often are you correct?

- A. ~90% of the time
- B. ~70% of the time
- C. ~50% of the time
- D. I have no idea

> [!note]- Reveal Answer
> **B. ~70% of the time (typical).** Most people are overconfident: they say 90% confident but are correct much less often. Calibration training improves this.

### Q17
Which cognitive bias most directly explains why we seek out information confirming our beliefs and avoid disconfirming evidence?

- A. Availability heuristic
- B. Confirmation bias
- C. Dunning-Kruger effect
- D. Anchoring

> [!note]- Reveal Answer
> **B. Confirmation bias.** The tendency to search for, interpret, and recall information in a way that confirms one's preexisting beliefs.

### Q18
**Scenario:** You just learned about a new cognitive bias. Over the next week, you notice it everywhere — in news articles, conversations, and even your own thinking. What is this phenomenon called?

- A. Frequency illusion (Baader-Meinhof phenomenon)
- B. Hindsight bias
- C. Selection bias
- D. Priming

> [!note]- Reveal Answer
> **A. Frequency illusion.** Once you learn something, selective attention makes it seem like it's appearing more often. This is also called the Baader-Meinhof phenomenon.

### Q19
The Dunning-Kruger effect describes:

- A. Overestimating the intelligence of others
- B. Underestimating one's own abilities due to imposter syndrome
- C. Low performers overestimating their ability and high performers underestimating theirs
- D. A statistical artifact of regression to the mean

> [!note]- Reveal Answer
> **C.** Low performers lack the metacognitive skill to recognize their incompetence; high performers assume tasks are easy for everyone.

### Q20
**Scenario:** You predict there is an 80% chance a specific paper will replicate. It fails to replicate. What is the most appropriate response?

- A. Discard the prediction model as wrong
- B. Record the miss and update your calibration
- C. Blame the replication for having a flawed design
- D. Maintain your confidence — one data point doesn't change the model

Your confidence in your chosen response:

`INPUT[number:q20_confidence]`%

> [!note]- Reveal Answer
> **B.** The goal of calibration is to track and improve over many predictions. A single miss is expected — even perfectly calibrated 80% predictions fail 20% of the time. Record, update, iterate.

---

## Scoring Guide

There are no "wrong" answers for calibration confidence, but the 20 factual questions have correct answers.

### Thread Scores

| Thread | Questions | Correct | /5 |
|--------|-----------|---------|-----|
| Logic & Reasoning | Q1–Q5 | | |
| Probability & Statistics | Q6–Q10 | | |
| Scientific Reasoning | Q11–Q15 | | |
| Metacognition & Calibration | Q16–Q20 | | |
| **Total** | **Q1–Q20** | | **/20** |

### Calibration Score

For the 4 confidence-slider questions (Q4, Q7, Q14, Q20), compare your confidence percentage to actual correctness. Good calibration means confidence ≈ accuracy.

| Question | Confidence % | Correct? (Y/N) |
|----------|-------------|----------------|
| Q4 | | |
| Q7 | | |
| Q14 | | |
| Q20 | | |

If you're above 80% confidence but got several wrong, you tend toward overconfidence. If below 50% but got most right, you tend toward underconfidence.

### Recommended Starting Month

| Total Score | Recommended Start | Notes |
|-------------|-------------------|-------|
| 18–20 | Month 02 or 03 | Strong foundations; accelerate |
| 14–17 | Month 01 | Solid; follow standard track |
| 10–13 | Month 01 (with review) | Consider extra time on Thread 2 or 3 |
| < 10 | Month 01 (dedicated) | Spend first 2 weeks on foundations |

### Related

- [[Curriculum/Curriculum Hub|Curriculum Hub]]
- [[Curriculum/Month 01/Month 01 MOC|Month 01 — Arguments & Foundations]]
- [[_templates/Claim|Claim Template]]
