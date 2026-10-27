# Step 5: Add the Basics

## Goal
Add the few fields that make the map usable: a website domain, and headcount and revenue where they're published. Do this only for rows that are in the market.

## Why it matters
A register tells you a company exists. A domain tells you how to reach it and lets later steps research it. Size data lets the user prioritise. Anything beyond this belongs in later repos.

## How
### Size and revenue
1. If the country publishes filed accounts (see the country profile), take headcount and revenue from the latest year available.
2. Record the year in `financials_year`. Figures from different years aren't comparable, so the summary should say how old they are.
3. Use `employees` for exact numbers only. If only a range is published, use `employees_range`.

### Domain
1. Look for the domain in the sources the user has access to. Some registers include a website field; many don't.
2. Where it has to be searched for, confirm the match before accepting it: the site should show the company's name, and ideally its register ID, address or legal name (often found in the footer, legal notice or imprint page).
3. Set `domain_confidence`:
   - `high`: the site shows the register ID or exact legal name and address
   - `medium`: the name and location match, but nothing unique confirms it
   - `low`: a plausible match that couldn't be confirmed
4. **If nothing matches, leave the domain empty.**

## Pitfalls
- **Similar names.** Many companies share a name or brand. A matching name alone isn't proof.
- **Groups and holding companies.** Several legal entities often share one website. Note this; don't treat it as an error.
- **Directory pages aren't websites.** A company's listing on a business directory isn't its domain.
- **Cost.** Domain search across thousands of rows can be slow or expensive. Agree the scope with the user first: all rows, one segment, or a sample.

## Done when
In-market rows have size data where it's published, and a domain with a confidence level or an empty field. Report how many rows got each.
