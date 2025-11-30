# Crop Yield Prediction under Climate Change

```markdown
## Data collection

Sources
- FAOSTAT — country-level crop statistics (production, area, yield).
- ECMWF (ERA5 / ERA5‑Land) — gridded climate predictors (temperature, precipitation, soil moisture, radiation), aggregated to monthly/seasonal.

Key processing (short)
- Harmonize country IDs and years; convert units.
- Aggregate ERA5 to countries (area‑weighted) and compute seasonal predictors(e.g., growing‑season mean temperature, cumulative precipitation).
- Run basic quality checks and minimal imputation; store cleaned tables for modelling.

Important
- Processed data, exact download queries, and preprocessing scripts are in /data and /scripts (provenance logged).
- Always cite FAOSTAT and ECMWF/ERA5 and follow their licensing/attribution.
```

