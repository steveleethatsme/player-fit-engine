# 02 · Fit model

Each factor produces an **explainable sub-score**: a number plus a short reason a user can read. Sub-scores roll up into two verdicts:

- **Immediate fit:** how well the player fits next season
- **Long-term fit:** how well he fits over the length of the contract

> Items marked **Open** are undecided and tracked in the [decision log](decisions/README.md). Nothing here is final.

---

## Phase 1: football fit

Each factor compares the player's **current context** with the **target club's**.

### F1 · League strength adjustment

**Why:** Stats from one league aren't worth the same in another.

- **Inputs:** player's current league, target club's league, per-90 stats
- **Output:** adjusted stats used by every other performance-based factor
- **Explanation example:** *"His output is adjusted down X% to reflect the step up from League A to League B."*
- **Open:** adjustment method and its data source (D-002)

### F2 · Tactical match

**Why:** A player suited to one system can struggle in another.

- **Inputs:**
  - possession share (current club vs. target club)
  - pressing intensity (current club vs. target club)
  - formation and the player's role in it
- **Output:** tactical sub-score
- **Explanation example:** *"Plays in a low-possession side; target club dominates the ball."*
- **Open:** which pressing metric to use, and how roles are defined per position

### F3 · Squad fit

**Why:** The same player can be a clear upgrade at one club and redundant at another.

- **Inputs:**
  - current starter and depth at his position at the target club
  - teammates or manager sharing his nationality or language
- **Output:** squad-fit sub-score, labelled **starter upgrade** / **rotation** / **depth**
- **Explanation example:** *"Would start over the current first choice; shares a language with two squad members."*
- **Open:** how "upgrade" is measured (same position-specific metrics as F5?)

### F4 · Experience & age profile

**Why:** Age and experience affect both readiness now and value over the contract.

- **Inputs:** age, minutes and appearances at senior level, level of competition played
- **Output:** feeds both verdicts differently. Experience weighs more for immediate fit; age trajectory weighs more for long-term fit.
- **Open:** how age curves are modelled per position

### F5 · Performance & trend

**Why:** Current level plus direction of travel.

- **Inputs:**
  - most recent season, using **position-specific key metrics**
  - 2–3 season trend to measure progression
- **Output:** performance sub-score and a trend label (improving / stable / declining)
- **Coverage:** all positions
- **Open:** the metric set per position, and minimum-minutes thresholds

---

## Phase 2: financial fit

Comes after football fit, and never overrides it.

| Factor | Compares |
|---|---|
| **Value** | Reported fee and wages vs. estimated market value |
| **Resale** | Resale potential over the contract length |
| **Alternatives** | Cost of the alternatives (other targets or internal options) |

- **Open:** market-value estimation method, and where wage data comes from

---

## Combining sub-scores

- **Open (D-003):** fixed weights vs. weights per position; whether users can adjust weights in the app
- **Required either way:** the final verdict must always show the contribution of each sub-score, so the explanation is never hidden behind the total.

## Output shape (draft)

```
Verdict: Player Y → Club X
  Immediate fit:  <score>  <label>
  Long-term fit:  <score>  <label>

  Sub-scores
    League adjustment   <score>  <reason>
    Tactical match      <score>  <reason>
    Squad fit           <score>  <reason>
    Experience & age    <score>  <reason>
    Performance/trend   <score>  <reason>
    [Phase 2] Financial <score>  <reason>
```
