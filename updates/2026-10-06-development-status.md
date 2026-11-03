---
schema_version: 1
type: general
date: 2026-10-06
title: "Five months in: both services run locally, production does not"
tags:
  - air-quality
  - urban-planning
  - interoperability
work_strand: WS2
authors:
  - name: "Konstantinos Despoinidis"
    organisation: "LIONCODE PC"
related_assets:
  - "https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/blob/main/TODO"
  - "https://github.com/LioncodeYourITPeople/ldt4ssc-geotwin/blob/main/docs/status.md"
---

Development of the GeoTwin ELBG platform started in the implementation
repository on 18 June 2026. By 6 October 2026 the local stack covers
the two services the pilot committed to. A longer snapshot is in
[docs/status.md](../docs/status.md).

## In the repository

- Ingestion from Copernicus CAMS, Sentinel, EEA, OSM, Eurostat, and
  reference geodata, with LDES views and compact PROV-O lineage.
- Service 1: LSTM forecasts, Random Forest risk scores, downscaling,
  SHAP, model cards, and a fairness check.
- Service 2: what-if scenarios, sensitivity studies with confidence
  intervals, and human review of proposals.
- Two Keycloak realms, ODRL share grants, federated alerts, and user
  manuals in English, Greek, and Bulgarian.
- MIM0 and MIM2 checked against MIMs Plus, with evidence in the repo.

## Not claimed

- No production deployment on IONOS, and no municipal user-acceptance
  test in Nestos or Sandanski.
- No citizen consultation and no co-design workshop is recorded in the
  repository history.
- Production disaster recovery (off-site backups, alerting, Keycloak
  production mode, stated RPO and RTO) is still open.
- CAMS backfill retrieves inside one time slot are still sequential.
- An old model file still fails without a clear message.
- The communication and sustainability report (PD5) belongs later in
  the pilot. It is not written.

The open items are tracked in the implementation repository `TODO`.
