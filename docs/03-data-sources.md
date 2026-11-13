# 03 · Data sources & licensing

## Policy

1. **Free public sources first.**
2. **Paid data** only where its license allows the intended use.
3. **Basic stats from a licensed third-party source** are possible, but **only within the terms of that subscription**.
4. A source is logged in the register below, **with its terms checked**, before any code depends on it.

## What each factor needs

| Factor | Data needed |
|---|---|
| F1 League strength | A way to rate leagues against each other |
| F2 Tactical match | Team possession share, a pressing-intensity measure, formations, player roles |
| F3 Squad fit | Squads by position, player nationalities and languages, manager nationality |
| F4 Experience & age | Birth dates, senior minutes and appearances, competition level |
| F5 Performance | Per-90 stats by season, position-specific metrics, 2–3 seasons of history |
| Phase 2 Financial | Reported fees and wages, market value estimates, contract lengths |
| Validation | Post-transfer minutes, per-90 output, whether the player stayed |

## Source register

Not filled in yet. Each candidate source gets researched and verified (coverage, history depth, terms) before it's added here. Nothing is listed from assumption.

| Source | Covers | History depth | Access | License / terms | Allowed uses | Verified on |
|---|---|---|---|---|---|---|
| *(none yet)* | | | | | | |

**Allowed uses** must be answered separately for each of:

- **Model:** can it be used to compute scores?
- **Display:** can raw values be shown in the app?
- **Public repo:** can derived outputs be published in the public repo?
- **FinalThird:** can outputs be shown inside FinalThird?

## Licensed third-party data

- Usage is limited to what the subscription terms allow. Those terms need to be confirmed in writing before any of it is used.
- Licensed data lives in `data/licensed/` (git-ignored) and is **never committed**.
- **Open (D-005):** whether results built from it can appear in the public repo or app.
