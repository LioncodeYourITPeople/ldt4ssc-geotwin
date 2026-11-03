---
schema_version: 1
type: milestone
date: 2026-06-26
title: "Service 1 machine-learning core is in the platform"
tags:
  - air-quality
  - climate-change
work_strand: WS2
authors:
  - name: "Konstantinos Despoinidis"
    organisation: "LIONCODE PC"
related_assets:
  - "https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/blob/main/docs/ml/README.md"
---

Service 1, the predictive environmental-health view, now has a training
and inference path in the repository.

## What we added

- A dataset build that turns ingested air-quality history, weather, and
  sidecar features into train, validation, and test tables.
- An LSTM forecaster aimed at 48–72 hour PM2.5 and NO2 forecasts.
- A Random Forest classifier for health-risk levels and red zones.
- API routes, a command-line entry point, and a schedule hook so
  inference can run without a manual step.
- A synthetic dataset generator so the path can be exercised before a
  long Copernicus history is loaded.

Forecasts and risk scores are published as NGSI-LD entities through
Scorpio. Training still depends on ingested history. A few days of
seeded rows are not enough for a stable LSTM.
