# Step 1: Define the Market

## Goal
Turn the user's description of who they sell to into rules a company register can actually apply.

## Why it matters
"Mid-sized manufacturers who care about sustainability" can't be filtered. A register only knows what was recorded when the company was registered and filed accounts. A market defined in recorded attributes can be counted, repeated and checked. A market defined in adjectives can't.

## How
1. Ask the user what they sell and who buys it. If they have customers, ask for a few examples of their best ones.
2. Translate the description into the attributes a register typically records:

| Attribute | Question to answer | Typical register field |
|---|---|---|
| Activity | What does the company do? | Primary industry code |
| Legal form | Which types of entity count? | Legal form |
| Status | Only active companies? | Status |
| Place | Whole country or certain regions? | Registered address / region |
| Age | Any minimum age? | Registration date |
| Size | Minimum headcount or revenue? | Filed accounts, if available |

3. For activity, find the industry codes that match. Start with the EU's NACE classification, then check whether the country uses a national version with more detail. List each code with its official description.
4. If the user has customers, ask for their registration numbers, not just names, and look up their codes and legal forms. Where real customers differ from the user's description, point it out. You won't know the official source until step 2, so treat these lookups as provisional and re-check them there. Third-party company databases are often out of date.
5. Split the market into **segments** if it naturally divides (for example by activity or size band). Each segment gets a short label.
6. Write the definition down in the worksheet below and get the user's sign-off.

## Worksheet
```
Market name:
Country:
Industry codes (code — description — segment):
Legal forms included:
Statuses included:
Regions included:
Minimum age:
Minimum size (only if the country publishes it):
Excluded on purpose (and why):
Signed off by user: yes / no, date
```

## Illustrative example
*An example only, to show the shape. It is not a recommended market.*

A user sells production-planning software to food producers. The description "food manufacturers with their own production" becomes:
- Industry codes: the NACE group for food manufacturing, split into segments such as "bakery", "dairy" and "meat processing"
- Legal forms: limited companies only, because sole traders rarely run a production line
- Status: active only
- Size: 10 or more employees, where filed accounts show it

## Pitfalls
- **Codes describe registration, not reality.** A company's primary code is what it declared, sometimes years ago. Some firms in your market will sit under a neighbouring code. Note this as a known gap; don't silently widen the market to compensate.
- **Too broad hides the signal, too narrow hides the market.** If one code is uncertain, make it a separate segment so it can be judged on its own.
- **Size filters depend on the country.** Not every country publishes headcount or revenue. Don't promise a size filter before step 2 confirms the data exists.

## Done when
The worksheet is filled in and the user has signed it off.
