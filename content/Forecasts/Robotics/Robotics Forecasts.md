---
tags:
  - moc
  - forecasts
---

# Robotics Forecasts

Predictions related to robotics, automation, and physical AI deployment.

## Active
```dataview
LIST confidence AS "Confidence", review_date AS "Next Review"
FROM #forecast
WHERE status = "active" AND contains(file.folder, "Forecasts/Robotics")
SORT review_date ASC
```

## Resolved
```dataview
LIST outcome AS "Outcome", confidence AS "Confidence"
FROM #forecast
WHERE status = "resolved" AND contains(file.folder, "Forecasts/Robotics")
SORT file.ctime DESC
```

## Related
- [[Forecasts/Forecasts|Forecasts]]
- [[Forecasts/Robotics/Humanoid robots major commercial deployment by 2035|Humanoid Robots by 2035]]
