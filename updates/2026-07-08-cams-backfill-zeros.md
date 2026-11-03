---
schema_version: 1
type: lesson
date: 2026-07-08
title: "A successful CAMS backfill can still be full of zeros"
tags:
  - air-quality
  - data-integration
work_strand: WS2
authors:
  - name: "Konstantinos Despoinidis"
    organisation: "LIONCODE PC"
related_assets:
  - "https://github.com/LioncodeYourITPeople/GeoTwin-ELBG/blob/main/docs/ingestion/README.md"
---

Our first Copernicus CAMS backfill jobs completed without error, and
most of the stored observations were zero. A green job is not evidence
that the values are usable for training.

## What went wrong

The pipeline treated a finished retrieve as success. Unit and model
level mismatches, and a static fill path, wrote rows that looked like
real history. Downstream dataset builds and the LSTM would have trained
on that history if we had not checked the numbers.

## What we changed

Through late July and early August we corrected the backfill, dropped
mock rows that had been standing in for live data, split air-quality
and weather into separate CAMS graphs, and fixed weather backfill
failures on their own. The check we kept is simple: after a backfill,
read a sample of PM2.5 and NO2 and confirm the values are not a flat
zero series before anyone trains a model.
