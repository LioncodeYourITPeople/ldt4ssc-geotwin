---
schema_version: 1
type: asset
date: 2026-09-01
title: "Free and open-source component inventory published"
tags:
  - interoperability
work_strand: WS2
authors:
  - name: "Konstantinos Despoinidis"
    organisation: "LIONCODE PC"
related_assets:
  - "https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/blob/main/docs/FOSS.txt"
---

We published a flat inventory of the free and open-source components
the platform runs on. It is `docs/FOSS.txt` in the implementation
repository.

## What it lists

The runtime and the libraries we actually import, each with its
licence. The list includes Keycloak, Garage, Scorpio, PostgreSQL,
TimescaleDB, PostGIS, FastAPI, the PyTorch and scikit-learn stack used
for the two models, SHAP, and Procrastinate. It is a bill of materials,
not an audit.

Component licences differ (Apache 2.0, MIT, BSD, AGPL, and others).
The inventory records each one. Code and documentation in this pilot
repository follow Apache 2.0 and CC BY 4.0. The implementation
repository does not yet have its own LICENSE file.
