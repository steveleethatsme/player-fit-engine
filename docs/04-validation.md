# 04 · Validation

The goal is to show the model is **more than an opinion engine**: players it rated as good fits should have done better after moving than players it rated as poor fits.

## Outcomes

For each past transfer, measured after the move:

| Outcome | Question |
|---|---|
| **Minutes** | Did he play more minutes? |
| **Output** | Did he hold or improve his per-90 output? |
| **Retention** | Did he stay at the club? |

Each outcome lines up with a verdict:

- **Immediate fit** → checked against first-season minutes and output
- **Long-term fit** → checked against retention and output across later seasons

## Proposed method

A starting design, not decided yet:

1. **Build a sample** of past transfers (see D-004 for which seasons and leagues).
2. **Score each transfer using only data available before the move.** No post-transfer information can leak into the inputs.
3. **Record the real outcomes** listed above.
4. **Compare:** do higher fit scores go with better outcomes? Report this per position as well as overall.
5. **Compare against simple baselines**, e.g. ranking by recent output alone, to show what the fit factors add.
6. **Keep a hold-out set** of seasons that isn't used while tuning weights.

## Definitions to settle (D-004)

- What counts as "more minutes": a share of available minutes, or compared to his previous season?
- What counts as "held output": the tolerance band for per-90 change after league adjustment
- What counts as "stayed": still at the club after N seasons? How loans and early sales are handled
- Minimum-minutes threshold for a transfer to be included

## Reporting

Validation results get published with the project, including where the model is wrong, so readers can judge it for themselves.
