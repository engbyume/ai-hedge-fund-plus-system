# System map and operating loop

The system is a context layer around a research and measurement loop.

```text
public sources
    -> source register and context package
    -> operator preference intake
    -> universe and catalyst research
    -> Chronos / TimesFM / Kronos optional forecasts
    -> exhaustion, insider, macro, availability, and overlap gates
    -> benchmark-normalized portfolio brief
    -> operator decision and action state
    -> redacted evidence and changelog
    -> updated context package
```

The loop is intentionally reversible. A forecast can be rejected. A candidate can remain a watchlist item. A proposed sale can be blocked when its paired buy or settlement condition is missing. The context package should explain those decisions instead of treating inaction as missing data.

## Canonical records

| Record | Required fields |
| --- | --- |
| Source | URL, owner, license or terms, retrieved date, role, confidence |
| Preference | benchmark, start date, risk, sectors, weights, schedule, delivery, trade authorization |
| Candidate | ticker, catalyst, catalyst date, evidence, countercase, invalidation, availability, forecasts |
| Action | side, ticker, amount or weight, paired action, settlement state, approval state |
| Observation | timestamp, portfolio return, benchmark return, spread, data freshness, cash-flow treatment |
| Decision | advice, operator choice, rationale, outcome, follow-up, unresolved uncertainty |
