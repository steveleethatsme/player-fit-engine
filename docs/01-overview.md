# 01 · Overview

## The question

> **Should Club X sign Player Y?**

Given any rumored transfer (e.g. *Antonio Nusa → Arsenal*), Player Fit Engine produces a fit verdict with an explanation for each factor behind it.

## Goals

1. **Stand-alone portfolio piece.** A working system plus an interactive web app, public on GitHub.
2. **FinalThird integration.** Plug into FinalThird later so users can check whether rumored signings are plausible.
3. **More than an opinion engine.** Validate the model on past transfers so its ratings can be checked against what actually happened.

## Principles

| Principle | What it means in practice |
|---|---|
| **Football first, money second** | Football fit is phase 1. Financial fit is phase 2 and never overrides a poor football fit. |
| **Explainable** | Every factor produces its own sub-score and a plain-language reason. No black-box single number. |
| **Two time horizons** | Every verdict reports **immediate fit** (next season) and **long-term fit** (over the contract). |
| **Validated** | Ratings are checked against real outcomes of past transfers (see [04-validation](04-validation.md)). |
| **License-clean** | Free public data first, paid data only where licensing allows (see [03-data-sources](03-data-sources.md)). |

## In scope

- All positions, each with its own key metrics
- Football fit: league strength, tactics, squad fit, experience/age, performance trend
- Financial fit (phase 2): fee and wages vs. value, resale potential, cost of alternatives
- Backtesting on past transfers
- Interactive web app

## Not yet decided

See the [decision log](decisions/README.md). Among other things: the tech stack, the data source for each factor, how sub-scores are combined, and the backtest sample.

## Visibility

The repo is **public** on GitHub as a portfolio piece and is developed in the open. Licensed data and anything its terms don't allow never goes into it.
