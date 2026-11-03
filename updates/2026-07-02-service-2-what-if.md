---
schema_version: 1
type: milestone
date: 2026-07-02
title: "What-if scenarios and proposal review are on the dashboard"
tags:
  - air-quality
  - urban-planning
  - mobility
work_strand: WS2
authors:
  - name: "Konstantinos Despoinidis"
    organisation: "LIONCODE PC"
related_assets:
  - "https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/blob/main/docs/ml/WhatIf.md"
---

Service 2 is usable from the dashboard. A municipal user can set a
what-if scenario, run a sensitivity study, and review a recommendation
before anything is treated as a decision.

## What we added

- A scenario page and a sensitivity study that ranks policy levers and
  returns a short narrative.
- A proposal workflow: model output becomes a proposal that a person
  reviews. Nothing is applied automatically.
- An analytics view for platform status, ingestion, and model artifacts.
- English and Greek in the dashboard.

Results are statistical estimates from historical relationships. They
are not a physical simulation of a future traffic scheme. Confidence
intervals on the recommendations followed in the next two weeks.
