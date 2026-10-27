# Step 6: Check Coverage

## Goal
Measure how much of the real market the map captures, and name what it misses.

## Why it matters
This is what separates a market map from a list. Any data provider can give you thousands of companies. Few can tell you whether that's 60% or 95% of the market. A coverage number lets the user trust the map, size the market honestly, and see where to look for what's missing.

## How
1. Find the official count of companies for the same industry codes and country, using the statistics source identified in step 2.
2. Match the definitions as closely as possible: same codes, same year, and, where the statistics allow, same legal forms and size bands.
3. Calculate coverage per segment and overall:
```
Coverage = companies in your map ÷ companies in official statistics
```
4. Report it in a table:
```
Segment         In map   Official count   Coverage   Notes
…               …        …                …          …
Total           …        …                …
```
5. List the known gaps: types of company you know are missing, and why.

## Reading the result
- **Coverage well below 100%:** look for a reason. Common causes are sole traders kept in a separate register, companies whose primary code differs from what they do, or a filter that removed too much.
- **Coverage above 100%:** usually a definition mismatch. Statistics often count only companies that were economically active during the year, while registers include everything registered as active. This often points to dormant companies.
- **No comparable statistics:** say so. Report the map without a coverage figure rather than inventing one.

## Pitfalls
- **The two sources count differently.** Statistics offices may count enterprises (economic units) rather than legal entities, and may use a different reference year. Note each difference you know of.
- **One number hides the story.** Overall coverage can look fine while one segment is badly covered. Always report per segment.

## Checkpoint
Show the user the coverage table and gaps. Agree whether the map is good enough for its purpose, or whether an earlier step needs revisiting.

## Done when
Coverage is reported per segment and overall, or its absence is explained, and the known gaps are listed.
