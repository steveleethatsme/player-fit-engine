# Decision log

Each decision gets an ID, a status, and once decided, a short record of **what was chosen and why**.

| ID | Decision | Status |
|---|---|---|
| D-001 | Tech stack: engine, API, web app | Open |
| D-002 | League strength adjustment: method and data source | Open |
| D-003 | How sub-scores combine: fixed vs. per-position weights, user-adjustable? | Open |
| D-004 | Backtest sample and outcome definitions (minutes, output, "stayed") | Open |
| D-005 | Licensed third-party data: what the public repo and app may show | Open |

## Template

Copy this into `D-00X-short-title.md` when a decision is made:

```
# D-00X · Title

Status: Decided (YYYY-MM-DD)

## Context
What problem this decision answers.

## Options considered
- Option A: pros / cons
- Option B: pros / cons

## Decision
What was chosen.

## Why
The reasoning, and the sources checked.

## Consequences
What this changes or rules out.
```
