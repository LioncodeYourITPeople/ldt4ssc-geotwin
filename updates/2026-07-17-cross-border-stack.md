---
schema_version: 1
type: milestone
date: 2026-07-17
title: "Cross-border identity, sharing, and model transparency are in the API"
tags:
  - air-quality
  - interoperability
  - data-integration
work_strand: WS2
authors:
  - name: "Konstantinos Despoinidis"
    organisation: "LIONCODE PC"
related_assets:
  - "https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/blob/main/docs/platform/Data-Sharing.md"
  - "https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/blob/main/docs/ml/Fairness.md"
  - "https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/blob/main/docs/ml/Downscaling.md"
---

The platform can now tell Nestos and Sandanski apart, and it can explain
a model output instead of only showing a score.

## Identity and sharing

- Keycloak has separate `nestos` and `sandanski` realms. Municipal staff
  and researchers stay in their home pilot. Admins can see both.
- Cross-pilot access is an ODRL grant on the REST API: request, decide,
  time-boxed grant, revoke. There is no separate Eclipse Dataspace
  Connector process.
- Pollution and risk alerts can be federated across the two pilots.
- GDPR jobs cover consent, export, and deletion paths, with a cookie
  notice on the dashboard.

## Models

- SHAP attributions on the LSTM and the Random Forest, shown with risk
  proposals.
- Model cards exposed on the DCAT-AP catalog.
- A fairness check across groups, and a statistical downscaling path
  (neighbourhood grid and a residual model) with an EEA comparison
  report. Live EEA station measurements are not wired in yet. The
  report runs on synthetic references until they are.
- Municipal vulnerability facilities (schools, hospitals, care homes)
  load as PointOfInterest features and can carry a vulnerability score.
- A KPI evidence endpoint counts forecasts, alerts, what-if runs, and
  sensitivity studies for later reporting.

These pieces support the pilot's data-management, interoperability, and
governance work. This note does not record a formal deliverable
submission to the consortium.
