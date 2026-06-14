---
tags:
  - moc
  - forecasts
---

# AI Forecasts

Predictions related to artificial intelligence capabilities, deployment, and impact.

## Active
```dataview
LIST confidence AS "Confidence", review_date AS "Next Review"
FROM #forecast
WHERE status = "active" AND contains(file.folder, "Forecasts/AI")
SORT review_date ASC
```

## Resolved
```dataview
LIST outcome AS "Outcome", confidence AS "Confidence"
FROM #forecast
WHERE status = "resolved" AND contains(file.folder, "Forecasts/AI")
SORT file.ctime DESC
```

## Related
- [[Forecasts/Forecasts|Forecasts]]
- [[Claim Analysis/Claim Analysis|Claim Analysis]]
