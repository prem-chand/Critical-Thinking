---
tags:
  - claim
confidence: 65
source: "Paper X"
date: "2025-01-01"
---

# Claim: Diffusion models will replace VAEs

## Source
- Paper X: "The Future of Generative Models"
- Discussions at NeurIPS 2024

## Evidence For
- Diffusion models achieve higher sample quality on image benchmarks
- Scalability to high resolutions with fewer artifacts
- Rapid adoption in industry (Stable Diffusion, DALL-E, Midjourney)
- Training stability advantages over GANs

## Evidence Against
- VAEs provide a principled latent space and likelihood-based training
- VAEs enable efficient encoding/decoding (useful for compression, representation learning)
- Hybrid approaches (e.g., latent diffusion) already borrow VAE-like components
- Diffusion is slow at inference time; distillation techniques are still maturing

## Assumptions
- That compute will remain cheap enough for iterative denoising at scale
- That latent space structure is less important than sample quality for most applications
- That no new architecture will emerge that combines the best of both

## Counterarguments
- "Replace" is too strong — more likely a complementary toolkit where each excels at different tasks
- Diffusion models may themselves evolve into something VAE-like (flow matching, consistency models)
- The history of ML shows that no single architecture dominates forever

## My Current Confidence
65%

## Confidence Log
| Date | Confidence | Reason for Change |
|------|-----------|-------------------|
| 2025-01-01 | 65% | Initial assessment — strong evidence but "replace" is a high bar |

## Related
- [[Claim Analysis/Claim Analysis|Claim Analysis]]
- [[Critical Thinking]]
