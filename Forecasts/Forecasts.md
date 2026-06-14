---
tags:
  - moc
  - forecasts
---

# Forecasts

Prediction is the ultimate test of critical thinking. It forces you to convert vague opinions into explicit probabilities — and then holds you accountable.

Good forecasters are distinguished not by intelligence, but by accurate uncertainty estimates. This is a core finding from [[Books/Superforecasting|Superforecasting]].

## Principles
- **Use explicit probabilities** — never "likely" or "probably." Use numbers.
- **Log your reasoning** — what evidence, what assumptions, what model.
- **Define update criteria in advance** — what would change your mind, and by how much.
- **Review regularly** — track accuracy, calibrate confidence, learn from misses.

## Forecast Categories
- [[Forecasts/AI/AI Forecasts|AI]]
- [[Forecasts/Robotics/Robotics Forecasts|Robotics]]

## Active Forecasts
```dataview
LIST confidence AS "Confidence", review_date AS "Next Review"
FROM #forecast
WHERE status = "active"
SORT review_date ASC
```

## Resolved Forecasts
```dataview
LIST outcome AS "Outcome", confidence AS "Confidence"
FROM #forecast
WHERE status = "resolved"
SORT file.ctime DESC
```

## Brier Score Tracking
A Brier score measures the accuracy of probabilistic predictions:
- Perfect: 0
- Random guessing: 0.25
- Always wrong: 1

Track yours over time to see if your calibration is improving.

## Related
- [[Claim Analysis/Claim Analysis|Claim Analysis]]
- [[Mental Models/Mental Models|Mental Models]]
- [[Books/Superforecasting|Superforecasting]]
- [[Critical Thinking]]
