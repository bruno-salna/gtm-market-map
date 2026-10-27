# Agent Instructions: Build a Market Map

You are building a **market map**: every company in a defined market in one country, taken from official records, filtered to the market and checked for coverage. You are not building a lead list. Lead lists come later, from this map.

Read this file first, then each step file in `steps/` in order. Work through them with your user.

## Principles
1. **Whole market first.** Start from the complete official record of companies, not from a search or a data provider's index. Only a complete starting point tells you what you're missing.
2. **Never guess.** If you can't find or confirm a value, leave it empty and say so. An honest gap is better than a confident error.
3. **Keep everything you remove.** Filtered-out rows stay in the file with the reason. The user must be able to see and question every cut.
4. **Show your counts.** Every step reports numbers: rows in, rows out, and why.
5. **The user decides the market; you find out the country.** Ask the user what they sell and to whom. Research the country's registers and rules yourself, then confirm with them.
6. **Respect licences.** If a source's terms don't allow the intended use, stop and tell the user. Don't work around it.
7. **Never ask for passwords or logins.** If a source needs an account, ask the user to download the data themselves and hand you the file.

## Two kinds of map
Step 2 decides which one you can build:
- **Full map:** the country publishes its company register in bulk, under terms that allow your use. You get every company, by name. Follow all seven steps as written.
- **Sizing map:** there's no lawful way to get the full set. You can still size the market from official statistics, and add a partial list of named companies where a licence-clean source exists. Steps 3–5 change; see [steps/03-pull-the-full-set.md](steps/03-pull-the-full-set.md).

A sizing map is a proper result, not a failure. Say clearly which kind you're building, and agree it with the user at the step 2 checkpoint.

## What to ask your user at the start
- What do you sell, and who buys it? (One or two sentences is enough to start.)
- Which country? (One country per map. Run the guide again for more.)
- Do you have a list of current customers? (It's optional, but it sharpens step 1.)
- What do you have access to: any paid data sources, tools, or budget for data?
- What will the map be used for? (Sizing, list building or territory planning: this changes how strict the filters should be.)

## Steps
| # | File | Output |
|---|---|---|
| 1 | [steps/01-define-the-market.md](steps/01-define-the-market.md) | A market definition the user signs off on |
| 2 | [steps/02-profile-the-country.md](steps/02-profile-the-country.md) | A filled-in [country-profile-template.md](country-profile-template.md) |
| 3 | [steps/03-pull-the-full-set.md](steps/03-pull-the-full-set.md) | A raw, untouched copy of the register |
| 4 | [steps/04-filter-to-the-market.md](steps/04-filter-to-the-market.md) | Every row marked in or out, with the reason, plus a funnel |
| 5 | [steps/05-add-the-basics.md](steps/05-add-the-basics.md) | Domain, size and revenue where they can be confirmed |
| 6 | [steps/06-check-coverage.md](steps/06-check-coverage.md) | A coverage percentage and a list of known gaps |
| 7 | [steps/07-output-the-map.md](steps/07-output-the-map.md) | `market-map.csv`, `market-map-full.csv` and `market-summary.md` |

**Checkpoints:** stop and confirm with the user after steps 1, 2 and 6. Those are where a wrong assumption costs the most.

## Working files
Keep each map in its own folder, named for the country and market (for example `de-food-manufacturers/`):
- `raw/`: the untouched downloads from step 3
- `scripts/`: any code you write, so the map can be rebuilt from fresh downloads
- the step outputs: market definition, country profile, coverage notes, the final files

Raw data and `market-map-full.csv` can run to hundreds of megabytes. Keep them out of version control; the scripts and the Markdown files are enough to rebuild them.

## When you're done
Go through [checklist.md](checklist.md). Every item must pass, or the summary must say why it doesn't.

## Output format
All rows follow [schema.md](schema.md). Don't rename or remove its columns.
