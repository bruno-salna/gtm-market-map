# Definition of Done

Every item passes, or the summary explains why it doesn't.

## Definition
- [ ] The market definition is written down and signed off by the user
- [ ] Every industry code included is listed with its description

## Source
- [ ] The kind of map (full or sizing) is stated and was agreed with the user
- [ ] The country profile is complete, with every answer linked
- [ ] The licence allows the intended use
- [ ] The raw copy is saved and unedited, with source, date and row count recorded

## Data
*For a sizing map, these apply to the partial list only, if there is one.*
- [ ] `market-map.csv` holds exactly the in-market rows
- [ ] Every row from the raw pull is in `market-map-full.csv`
- [ ] Both files follow [schema.md](schema.md), with no renamed or missing columns
- [ ] `register_id` is unique within the country
- [ ] Every row has `in_market` set. Every excluded row has `excluded_by`.
- [ ] Every in-market row has `segment`
- [ ] No field was filled with a guess
- [ ] If domains were added, every domain has a `domain_confidence`. If they were skipped, the summary says so at the top.
- [ ] Names with accents or non-Latin characters display correctly

## Summary
- [ ] The funnel adds up: rows in − removed = rows out, at every filter
- [ ] Coverage is reported per segment, or its absence is explained
- [ ] Known gaps are listed
- [ ] Every judgment call agreed with the user is recorded under "Decisions made"
- [ ] Data age (pull date and financials year) is stated at the top
