# Step 3: Pull the Full Set

## Goal
Get a complete, untouched copy of the register for the country, or of the largest part of it the access route allows.

## Why it matters
The whole point of a market map is knowing what you didn't select. If you pull only search results, you can't measure coverage later. Pull everything; filtering happens in step 4.

## How
1. Pull the full register through the route confirmed in step 2.
2. **Save the raw copy and never edit it.** All later work happens on a working copy. If something goes wrong, you start again from the raw file.
3. Record where it came from:
```
Source:
Access route:
Date pulled:
Source version or publication date (if given):
Licence:
Rows:
```
4. If the data is split across several files (for example companies, addresses and activities), join them on the register ID. Note how many rows failed to join.
5. For large registers, process in chunks rather than loading everything at once.

## Checks
- **Row count:** does it roughly match the total the register publishes? If it's far off, find out why before moving on.
- **Unique IDs:** each register ID should appear once. Duplicates usually mean a join went wrong or history rows were included.
- **Field fill rate:** for the fields you need (code, status, legal form), how many rows have a value? Note the percentages.
- **Characters:** check that names with accents or non-Latin characters look right. Broken characters mean the wrong file encoding.

## Pitfalls
- **History rows.** Some registers include past versions of each company. Keep only the current record, unless the user needs the history.
- **Silent truncation.** APIs and exports often cap results. If the count is a round number, suspect a limit.

## If you're building a sizing map
There's no full set to pull. Instead:
1. **Pull the official counts** for the market's industry codes, region and size bands. These become the market size. Note the year, the classification version, and the unit counted (legal entities or enterprises).
2. **If the statistics need an account,** ask the user to download the tables and give you the files.
3. **Optionally, pull a partial list** of named companies from any licence-clean source agreed in step 2. Keep each source's raw copy and record it as above.
4. Carry on with step 4 for the partial list only. Step 5 applies to the partial list. In step 6, coverage becomes "named companies ÷ official count".

## Done when
A raw copy is saved, the source is recorded, and all four checks are reported. For a sizing map: the official counts are saved with their source and year, plus any partial list.
