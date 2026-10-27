# Step 4: Filter to the Market

## Goal
Mark every row as inside or outside the market from step 1, and record why.

## Why it matters
The filter funnel (how many companies each rule removed) is half of what makes the map useful. It shows the user the shape of their market and lets them question any rule that cut too much.

## How
1. Map the register's statuses to `status_normalised` using the country profile.
2. Apply the filters **in this order**, each to the rows that survived the one before:
   1. Status
   2. Legal form
   3. Industry code
   4. Region
   5. Age
   6. Size (only if step 2 confirmed the data exists)
3. For each row, set `in_market` to `true` or `false`. For excluded rows, set `excluded_by` to the first filter that removed it.
4. **Keep the excluded rows** in the file. Never delete them.
5. Set `segment` for every row that's in the market.
6. Report the funnel:

```
Filter          Rows in   Removed   Rows out
Status          …         …         …
Legal form      …         …         …
Industry code   …         …         …
Region          …         …         …
Age             …         …         …
Size            …         …         …
In market                           …
```

## Pitfalls
- **Active on paper, dormant in reality.** Many companies are registered as active but trade little or not at all. Signs include no filed accounts for several years, or filed accounts with no revenue. Flag these rather than silently removing them, and agree a rule with the user.
- **Liquidation has many names.** Insolvency, liquidation, bankruptcy and striking-off are often separate statuses. Check each against the profile.
- **Missing values.** Decide with the user whether a row with no industry code or no size data is in or out. Don't decide quietly. Report how many rows the decision affects.
- **Size filters remove the unknowns too.** If many companies don't file accounts, a size filter removes them along with the small ones. Report both numbers separately.

## Done when
Every row has `in_market` set, excluded rows have `excluded_by`, in-market rows have `segment`, and the funnel is reported.
