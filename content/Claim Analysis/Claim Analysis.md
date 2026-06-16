---
tags:
  - moc
  - claim-analysis
---

# Claim Analysis

A personal rationality lab. Every time I encounter an interesting claim, I create a note analyzing the evidence, assumptions, counterevidence, and my current confidence.

The goal is to track how beliefs change over time — and get better at calibrating confidence.

## Active Claims
```dataview
LIST
FROM #claim
WHERE confidence != 100 AND confidence != 0
SORT file.ctime DESC
```

## Resolved Claims
```dataview
LIST
FROM #claim
WHERE confidence = 100 OR confidence = 0
SORT file.ctime DESC
```

## All Claims
```dataview
LIST confidence AS "Confidence", source AS "Source"
FROM #claim
SORT confidence DESC
```

## Related
- [[Critical Thinking]]
- [[Biases/Cognitive Biases|Cognitive Biases]]
- [[Forecasts/Forecasts|Forecasts]]
