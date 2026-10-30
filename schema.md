# Shared Row Schema

This is the output format for every repo in the series: Market map → List quality → ICP + tiering → Signals → Orchestrator. Each repo reads and writes rows in this format, which is what lets them chain. Each repo also works on its own.

## Rules
- **File:** CSV, UTF-8, comma-separated, one header row. Keep the original characters in names (ä, ł, ō …); don't strip accents.
- **Column names:** `snake_case`, exactly as listed below.
- **Empty means unknown.** Never fill a field with a guess. A blank field is honest; a wrong value spreads into every later step.
- **One row per legal entity,** identified by `country` + `register_id`.
- **Don't drop columns you don't use.** Later repos may need them.
- **Add only within your prefix.** Each repo owns a prefix for any columns it adds (see the end of this file).

## Columns written by the Market map

### Identity
| Column | Type | Meaning |
|---|---|---|
| `country` | text | ISO 3166-1 alpha-2 code, e.g. `DE`, `PL` |
| `register_id` | text | The company's identifier in the national register. Store it as text so leading zeros survive. |
| `legal_name` | text | Name exactly as registered. Cleaning happens in the List quality repo. |
| `legal_form` | text | Legal form as the register writes it, e.g. `GmbH`, `sp. z o.o.` |
| `status` | text | Status as the register writes it |
| `status_normalised` | text | One of `active`, `inactive`, `in_liquidation`, `unknown` |
| `registered_date` | date | `YYYY-MM-DD` |

### Classification and place
| Column | Type | Meaning |
|---|---|---|
| `industry_code` | text | Primary activity code as registered |
| `industry_code_system` | text | Which classification and version, e.g. `NACE Rev. 2.1` or the national variant |
| `region` | text | First-level region as the register writes it |
| `city` | text | City or municipality |

### Size and web
| Column | Type | Meaning |
|---|---|---|
| `employees` | integer | Exact headcount from filed accounts. Leave empty if only a range is known. |
| `employees_range` | text | Range, if that's all the source gives, e.g. `10-49` |
| `revenue` | number | Annual revenue, in the currency below |
| `revenue_currency` | text | ISO 4217 code, e.g. `EUR` |
| `financials_year` | integer | The year the employee and revenue figures refer to |
| `domain` | text | Bare domain, e.g. `example.com`. No `https://`, no `www.` |
| `domain_confidence` | text | `high`, `medium`, `low`, or empty if no match |

### Market map fields
| Column | Type | Meaning |
|---|---|---|
| `in_market` | boolean | `true` if the row passed every filter |
| `excluded_by` | text | Name of the first filter that removed the row. Empty if `in_market` is `true`. |
| `segment` | text | The segment label from the market definition |
| `source_name` | text | Which source the row came from (the user's own source, named in the country profile) |
| `source_date` | date | When the source data was pulled, `YYYY-MM-DD` |

## Columns other repos add
| Repo | Prefix | Examples |
|---|---|---|
| List quality | `quality_` | `quality_display_name`, `quality_duplicate_of`, `quality_usable`; full list in its [schema](https://github.com/bruno-salna/gtm-list-quality/blob/main/schema.md) |
| ICP + tiering | `icp_`, `tier` | `icp_score`, `icp_reasons`, `tier` |
| Signals | `signal_` | `signal_type`, `signal_date`, `signal_note` |
| Orchestrator | `run_` | `run_id`, `run_step` |
| (input columns) | `src_` | Input columns that don't map to the schema, kept as they came |
