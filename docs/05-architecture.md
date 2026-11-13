# 05 · Architecture

> Draft. The tech stack isn't chosen yet (D-001). This describes components and data flow only.

## Data flow

```
 Sources ──► Ingestion ──► Normalization ──► Features ──► Scoring ──► Explanations ──► API ──► Web app
 (public,      (fetch,       (IDs, seasons,    (per-90,     (sub-scores,   (plain-language          │
  licensed)     cache)        league adj.)      trends,      verdicts)      reasons)                └─► FinalThird
                                                tactics)
                                     ▲
                                     └── Validation harness (backtests on past transfers)
```

## Components

| Component | Folder | Responsibility |
|---|---|---|
| **Ingestion** | `engine/` | Fetch from each registered source; cache locally in `data/raw/` or `data/licensed/` |
| **Normalization** | `engine/` | Match player, club and league IDs across sources; align seasons; apply league strength adjustment (F1) |
| **Features** | `engine/` | Per-90 stats, position-specific metrics, 2–3 season trends, team tactical profiles, squad depth charts |
| **Scoring** | `engine/` | One module per factor (F1–F5, later financial). Each returns a sub-score plus a reason |
| **Verdicts** | `engine/` | Combine sub-scores into immediate and long-term fit |
| **Validation** | `engine/` + `notebooks/` | Backtest harness using only pre-transfer data |
| **API** | TBD | Serves verdicts to the web app and later to FinalThird |
| **Web app** | `web/` | Pick club and player, see verdicts and sub-score breakdowns |

## Design rules

1. **Each factor is its own module** with the same interface (inputs → sub-score + reason), so factors can be added, removed or re-weighted on their own.
2. **Pin the data date.** Every score records which data snapshot it used, so backtests are reproducible.
3. **The licensed-data boundary is enforced in code.** Anything derived from licensed data is tagged so it can be filtered out of public outputs.
4. **FinalThird integration happens through the API only.** No shared database, so this project can stand on its own.

## Open

- **D-001:** language and framework for the engine, the API and the web app
- Storage for features (files vs. a database)
- Hosting for the public demo
