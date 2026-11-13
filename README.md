# Player Fit Engine

**Should Club X sign Player Y?**

Player Fit Engine scores whether a rumored transfer makes sense for the buying club, e.g. *Antonio Nusa → Arsenal*. Fit is judged **football-first, money second**, and every factor produces an explainable sub-score so users can see *why* a player fits or doesn't.

It reports two verdicts:

- **Immediate fit:** next season
- **Long-term fit:** over the length of the contract

> **Status:** pre-alpha, design phase. Developed in the open as a portfolio project.

## How fit is judged

| Area | Phase | What it compares |
|---|---|---|
| League strength adjustment | 1 | Stats in one league aren't worth the same in another |
| Tactical match | 1 | Possession share, pressing intensity, formation and role |
| Squad fit | 1 | Upgrade on the starter or depth? Teammate or manager sharing nationality/language? |
| Experience & age profile | 1 | Career stage relative to the club's needs |
| Performance | 1 | Most recent season, plus a 2–3 season trend, using position-specific key metrics (all positions) |
| Financial fit | 2 | Reported fee and wages vs. estimated market value, resale potential over the contract, cost of alternatives |

The full design is in [`docs/02-fit-model.md`](docs/02-fit-model.md).

## Validation

The model is backtested on past transfers. Did players it rated as good fits:

1. play more minutes,
2. hold or improve their per-90 output, and
3. stay at the club?

See [`docs/04-validation.md`](docs/04-validation.md).

## Repository layout

```
player-fit-engine/
├── docs/          Design docs and decision log
├── engine/        Scoring engine (data → features → sub-scores → verdicts)
├── web/           Interactive web app
├── data/          Local data workspace (raw and licensed data are git-ignored)
├── notebooks/     Exploration and validation analysis
└── tests/         Tests for the engine
```

The tech stack hasn't been chosen yet. See [`docs/decisions/`](docs/decisions/).

## Docs

1. [Overview](docs/01-overview.md)
2. [Fit model](docs/02-fit-model.md)
3. [Data sources & licensing](docs/03-data-sources.md)
4. [Validation](docs/04-validation.md)
5. [Architecture](docs/05-architecture.md)
6. [Roadmap](docs/06-roadmap.md)
7. [Decision log](docs/decisions/README.md)

## Integration

Built to stand on its own first, then plug into **FinalThird** so users can check whether rumored signings are plausible.

## License

Code is released under the [MIT License](LICENSE). Third-party data is never covered by this license and is never committed (see [`data/README.md`](data/README.md)).
