# Step 7: Output the Map

## Goal
Deliver the map itself, the full set of rows behind it, and a one-page summary someone can read in two minutes.

## How
### `market-map.csv`
- The in-market rows only, following [../schema.md](../schema.md). This is the file people work with.
- Sorted by `segment`, then `legal_name`.

### `market-map-full.csv`
- Every row from step 3, in and out of the market, in the same columns. This is where the excluded rows and their reasons are kept.
- Sorted by `in_market` (true first), then `segment`, then `legal_name`.
- It can be very large (a whole national register). Keep it out of version control.

### `market-summary.md`
Use this structure:

```
# Market map: <market name>, <country>

Pulled: <date> from <source>. Financial figures from <year(s)>.

## Size
Total in market: …
<table: segment — companies — share of market>

## How we got here
<funnel table from step 4>

## Coverage
<coverage table from step 6>
Known gaps:
- …

## Data completeness (in-market rows)
Domain found: …% (high …, medium …, low …)
Headcount known: …%
Revenue known: …%

## Decisions made
- <each judgment call agreed with the user, e.g. how missing codes were treated>

## Caveats
- …
```

See [../examples/](../examples/) for a made-up filled-in version.

### For a sizing map
- Say so in the first line of the summary: "Sizing map: counts from official statistics; no full company list is available in this country."
- The Size section uses the official counts, by segment and size band.
- `market-map.csv` holds only the partial list of named companies, if there is one. Without a partial list, skip the CSV files.
- Under Caveats, explain why a full map wasn't possible and what it would take (cost, permission or time).

## Pitfalls
- **Don't oversell.** If coverage is unknown or data is thin, say so at the top, not in a footnote.
- **Record the decisions.** Someone rerunning the map in six months needs to know what was decided and why.

## Done when
Both files exist, and [../checklist.md](../checklist.md) passes.
