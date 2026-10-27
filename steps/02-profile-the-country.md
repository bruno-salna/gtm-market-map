# Step 2: Profile the Country

## Goal
Find out how this country records its companies, so the market definition from step 1 can be applied to real data.

## Why it matters
Every EU country keeps a business register, but they differ in what they publish, how you can access it, and what you're allowed to do with it. Getting this wrong means building on data you can't use or don't understand.

## How
Fill in [../country-profile-template.md](../country-profile-template.md) by researching the country yourself. Use official sources first: the register's own site, the government's open-data portal and the national statistics office.

Work through it in this order:
1. **Find the register.** Which body keeps the official record of companies? There may be more than one (for example a separate one for sole traders).
2. **Find how to access it.** Bulk download, API, search-only website, or paid access through a licensed reseller.
3. **Read the licence.** Can the data be downloaded in bulk, stored, and used commercially? Note the exact terms and link to them.
4. **List the fields.** What does each record contain? Map them to the columns in [../schema.md](../schema.md).
5. **Check the codes.** Which industry classification and version does the register use? Is the primary activity always filled in?
6. **List legal forms and statuses** as the register writes them, and map each status to `active`, `inactive`, `in_liquidation` or `unknown`.
7. **Find financial data.** Are annual accounts filed publicly? Which companies must file, and do they include headcount and revenue?
8. **Find the official statistics.** Does the statistics office publish company counts by industry code? These are needed in step 6.
9. **Re-check the user's customers** from step 1 against the official source, and correct anything the provisional lookup got wrong.

## Decisions
- **If there's no lawful bulk access** (no download, or terms that forbid building lists): tell the user, and lay out the options with cost, time and what each one gives:
  - a **sizing map** from official statistics (see [../AGENT.md](../AGENT.md), "Two kinds of map");
  - other official registers that list the market directly, for example a licence register for a regulated trade, if their terms allow bulk use;
  - a paid source;
  - asking the data holder for access or permission.

  Let the user choose. Don't keep searching for workarounds once the options are clear.
- **Watch for use restrictions as well as licences.** Some sellers license data for one-time use only (common with address lists). That data can't be stored in a map. Say so before the user pays for it.
- **If the licence forbids the intended use: stop.** Explain it to the user and don't continue with that source.
- **If the register has no industry codes,** or they're mostly empty, tell the user. Step 1's definition may need another route, such as the statistics office or the tax authority.

## Pitfalls
- **Official sites and third-party copies look alike.** Many sites republish register data. Prefer the official source, and note where you got it.
- **Fields change over time.** Legal forms and status codes get renamed. Look for the register's own documentation or codebook.
- **"Free to search" doesn't mean "free to download".** Check the terms for bulk use separately.

## Checkpoint
Show the user the filled-in profile. Confirm the access route and licence before pulling any data.

## Done when
Every section of the profile is filled in or marked "not available", and the user has confirmed the access route.
