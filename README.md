# Market Map

**An agent-ready guide to mapping a whole B2B market in any EU country, from official company records, before any outreach.**

Most list building starts with a data provider's search: you get the companies they happen to have indexed, and you never learn what's missing. This guide works the other way round. Start from the complete official record of companies, filter it down to your market, and measure how much of the real market you've captured.

The result is a market map: every company in the market, the funnel that got you there, and a coverage figure you can defend.

## How to use it
This repo contains no code and no data. It's a set of instructions for an AI agent.

1. Fork or clone this repo.
2. Give it to your agent (Claude, ChatGPT, Cursor or any other) and point it to [AGENT.md](AGENT.md).
3. The agent asks what you sell and in which country, researches that country's registers itself, and works through the seven steps with you.

You supply the market and the country. The agent works out the rest and checks with you at the points that matter.

**What you get depends on the country.** Where the company register can be downloaded in bulk, you get a full map: every company, by name. Where it can't, you get a sizing map: the market size from official statistics, plus whatever named companies can be listed from licence-clean sources. The agent tells you which one is possible before any data is pulled.

## The seven steps
| # | Step | What happens |
|---|---|---|
| 1 | [Define the market](steps/01-define-the-market.md) | Turn "who we sell to" into attributes a register records |
| 2 | [Profile the country](steps/02-profile-the-country.md) | Find the register, access route, licence, fields and statistics |
| 3 | [Pull the full set](steps/03-pull-the-full-set.md) | Get the whole register, untouched |
| 4 | [Filter to the market](steps/04-filter-to-the-market.md) | Mark every company in or out, with the reason |
| 5 | [Add the basics](steps/05-add-the-basics.md) | Domain, headcount and revenue, with confidence levels |
| 6 | [Check coverage](steps/06-check-coverage.md) | Compare with official statistics; name the gaps |
| 7 | [Output the map](steps/07-output-the-map.md) | The map, the full set of rows behind it, and a one-page summary |

## Why "whole market first"
- **You can size the market honestly.** "There are 1,840 active companies in this segment" beats "our provider returned 600".
- **You can see what you're missing.** Coverage turns a list into something you can trust.
- **Every later step improves.** Scoring, tiering and signals all work better on a complete, well-defined base.

## Part of a series
This is the first of five guides that chain together through a [shared row schema](schema.md):

**Market map** → [List quality](https://github.com/bruno-salna/gtm-list-quality) → ICP + tiering → Signals → Orchestrator

Each guide works on its own. Used together, each one picks up the previous one's output.

## What's in the repo
```
AGENT.md                      start here (for the agent)
steps/                        one file per step
country-profile-template.md   filled in by the agent for each country
schema.md                     output columns, shared across the series
checklist.md                  definition of done
examples/                     made-up sample output
LICENSE                       MIT
```

## Influences
The guide is written from scratch. It draws mainly on my own work building lead lists for companies selling into European markets, and it also learned from public work:

- **Eric Nowoslawski, [coldoutboundskills](https://github.com/growthenginenowoslawski/coldoutboundskills)** (MIT).
  - `list-builder` treats building a list as one end-to-end job, from discovery through checking.
  - `auto-research-public` makes the agent pause for a human before key decisions. The checkpoints after steps 1, 2 and 6 follow that idea.

Where this guide goes its own way: most list-building playbooks start from what data providers have indexed. This one starts from official company records, so you can measure how much of the real market you've covered before any outreach.

## Licence
[MIT](LICENSE). Use it, fork it, adapt it, including commercially; keep the copyright notice.
