---
tags:
  - claim
confidence: 55
source: "Various papers on scaling laws"
date: "2025-01-01"
---

# Claim: Scaling RL (not just pretraining) will be the primary driver of AI capability gains by 2030

## Source
- Scaling laws papers (Kaplan et al., Hoffmann et al.)
- OpenAI o1/o3 system cards
- DeepSeek-R1 paper
- Discussions in AI alignment and capabilities research communities

## Evidence For
- OpenAI's o-series models show substantial gains from RL-based reasoning
- DeepSeek-R1 demonstrates that pure RL can induce reasoning behaviors
- Pretraining data may hit a wall (finite internet data, legal constraints)
- RL enables self-play and synthetic data generation, breaking the data bottleneck
- RL directly optimizes for outcomes rather than next-token prediction

## Evidence Against
- Pretraining is the foundation; RL only works on top of strong pretrained models
- RL is notoriously unstable and hard to scale reliably
- Current RL techniques (RLHF, GRPO) are still brittle and reward-hackable
- Gains from RL may saturate faster than pretraining gains
- The most impressive capabilities still correlate strongly with pretraining compute

## Assumptions
- That pretraining data scarcity will become a binding constraint
- That RL stability issues can be solved at scale
- That reward specification for general capabilities is tractable
- That no fundamentally new paradigm emerges (e.g., active inference, new architectures)

## Counterarguments
- RL and pretraining are complementary, not competing — framing it as "primary driver" may be a false dichotomy
- The real driver might be architecture innovations, not training methodology
- Synthetic data from RL may reduce in quality over multiple generations (model collapse)

## My Current Confidence
55%

## Confidence Log
| Date | Confidence | Reason for Change |
|------|-----------|-------------------|
| 2025-01-01 | 55% | Initial — RL is clearly important, but "primary driver" is a strong claim |

## Related
- [[Claim Analysis/Claim Analysis|Claim Analysis]]
- [[Claim Analysis/Diffusion models will replace VAEs|Diffusion vs VAE]]
- [[Critical Thinking]]
