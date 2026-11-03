---
schema_version: 1
type: milestone
date: 2026-07-08
title: "Maps run on PostGIS, and the dashboard passed an accessibility pass"
tags:
  - air-quality
  - urban-planning
work_strand: WS2
authors:
  - name: "Konstantinos Despoinidis"
    organisation: "LIONCODE PC"
related_assets:
  - "https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/blob/main/docs/platform/Map-Layers.md"
  - "https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/blob/main/dashboard/docs/accessibility-audit.md"
---

The map no longer depends on GeoServer. Layers, GeoJSON vectors, and
raster tiles are served by the REST API from PostGIS. The dashboard
also went through an accessibility pass in the same week.

## Maps

- PM2.5 heatmap and station or facility symbols on the layers map.
- Scenario maps use model site coordinates and can show facility
  overlays.
- Region-specific raster legends for the indicator layers.

GeoServer was removed from the compose stack on 6 July 2026.

## Accessibility

Pull request #2 covered the dashboard against WCAG 2.1. Automated axe
checks and the fixes from that pass are in the repository, including
authenticated pages, not only the public routes. The audit notes live
with the dashboard.
