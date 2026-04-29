# Operating Rhythms

Files do not stay current by accident. The Orchestration Framework defines three mandatory rhythms that keep the system honest. Skipping them is the most reliable way to wake up six months in and find that the vault no longer reflects reality, the active sprint is two weeks stale, and the constitution is contradicting current behavior.

The three rhythms operate on different timescales and serve different purposes.

| Rhythm | Cadence | Primary purpose |
| --- | --- | --- |
| [Daily](daily.md) | Every day | Ingest the day's signal, capture in real time, close the loop at end of day |
| [Weekly](weekly.md) | Every Sunday (or operator's chosen day) | Review last week's shipping, set next week's focus, triage the idea bank |
| [Monthly](monthly.md) | Every month | Audit the framework itself, review aging decisions, prevent cathedral drift |

## Why three rhythms

Each rhythm catches a different category of drift. The daily rhythm prevents capture loss — ideas, tasks, and reflections that would otherwise dissolve before reaching the vault. The weekly rhythm prevents priority drift — the active sprint slowly diverging from what the operator actually intends to ship. The monthly rhythm prevents cathedral drift — the framework itself accumulating components that no longer serve the work.

Adopters tempted to drop the monthly rhythm should resist. It is the only mechanism that prevents the framework from becoming a system the operator serves rather than a system that serves the operator. Of the three rhythms, monthly is the one most likely to be skipped and the most expensive to skip.

## Cadence customization

The specific times and days named in each rhythm file are the framework's defaults, not absolutes. Adopt the cadence; adapt the schedule to your context. A morning brief at 06:00 is a recommendation, not a requirement. What matters is that the rhythm runs reliably on whatever schedule the operator commits to and integrates with their actual life.

The one part that is non-negotiable is the *existence* of all three rhythms. Operators who run daily and weekly but skip monthly are running a degraded framework that will look fine for the first three months and then quietly accumulate drift.
