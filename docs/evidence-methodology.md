# Evidence methodology

## Measurement contract

Use one benchmark, one declared start date, one return method, and consistent treatment of cash flows. The default example uses SPY as the investable proxy for the S&P 500. A valid comparison should identify whether it is time-weighted or money-weighted, how deposits and withdrawals are handled, and whether transaction costs, taxes, dividends, and cash are included.

The public table reports percentage returns and spreads only. `spread = portfolio return - benchmark return` for the same period.

## Historical selector accuracy

For historical selection diagnostics, exact-pair hit rate is `qualified windows / evaluated windows`. A window qualifies only when both distinct non-proxy picks land in the realized full-market top 30. Preserve the Cash App top-65 prefilter, strict prior-label cutoff, route and market-type checks, and exact-two selection.

Compare candidate accuracy only on identical decision and label sessions. Report route-level results and the longest consecutive qualified streak. This diagnostic is separate from portfolio returns and cannot replace the five-consecutive-week promotion gate.

## Evidence labels

- `machine_observed`: extracted from an archived report or deterministic run.
- `user_confirmed`: explicitly supplied by the operator, such as a purchase or rejection.
- `public_source`: supported by a public URL.
- `inference`: a reasoned interpretation that is not directly proven.
- `unverified`: a claim that needs a baseline, readback, or source before it can be measured.

## Momentum and catalyst evidence

An individual-stock candidate needs a company-specific catalyst with a date or persistence window, supporting evidence, a countercase, and an invalidation signal. Momentum is evaluated using all five daily returns, green/red breadth, late-versus-early momentum, and the largest positive day's share of the positive five-day move.

If the largest positive day contributes 60% or more of the positive five-day move, reject the candidate from the weekly replacement watchlist as a concentration and exhaustion risk. The 60% threshold is a hard exclusion in this system, not a reason to increase confidence.

## Benchmark interpretation

One positive spread is not proof of a durable edge. The evidence should show multiple checkpoints, market direction, drawdown, downside capture, and data quality. A neutral or zero spread may be low-information if the report was incomplete, reset, or produced on a non-comparable date.

## Evidence gaps

If the baseline is missing, say so. If the broker value is pending, say so. If a platform is not independently confirmed, retain `Manual Cash App search required` or the equivalent status. If a sale is recorded without a paired buy, block publication and correct the plan before delivery.
