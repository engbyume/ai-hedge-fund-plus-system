# Decision log

This log records what the system advised, what Jeremy chose, why the system changed, and what remains unproven. It separates advice from execution and outcome.

## 2026-07-11 - Trial start reported, baseline not archived

- Advice received: begin a two-month benchmark trial and compare the custom portfolio with the S&P 500 proxy.
- Jeremy's decision: start the experiment with a custom mix intended to avoid fixed benchmark sector concentration.
- System change: establish a review window and a benchmark comparison section.
- Verification: later reports reference the start date, but an independently archived 2026-07-11 baseline is not present.
- Unproven: cumulative return and the user's later estimate of approximately 3% outperformance.

## 2026-07-18 - First archived checkpoint

- Advice received: continue the custom allocation while monitoring month spread and downside behavior.
- Evidence: archived report showed a +1.72 percentage-point month spread versus SPY, with the benchmark down over the month.
- Jeremy's decision: continue the trial rather than declare victory.
- System change: retain benchmark, day, week, and month fields in the report.
- Verification: the checkpoint is published in the percentage-only table.
- Unproven: whether the spread came from intentional diversification, timing, or noise.

## 2026-07-19 through 2026-07-26 - Catalyst and breadth hardening

- Advice received: broaden the Cash App screening universe, research company catalysts, and penalize exhaustion instead of ranking raw trailing returns.
- Jeremy's decision: keep the system focused on individual catalysts and custom sector exposure, while requiring platform availability to be confirmed separately.
- System change: retained a broad 700-row screening universe, added five-day returns, breadth, late-versus-early momentum, exhaustion fields, catalyst context, countercase, and invalidation signals.
- Verification: focused tests and dry renders passed in the private runtime; raw reports and candidate files are not published.
- Unproven: whether the expanded universe improves realized returns after costs and execution constraints.

## 2026-07-27 - Cross-market risk haircut

- Advice received: scan energy, shipping, rates, currency, credit, geopolitical, and policy proxies for unscheduled shocks that could affect a candidate's sector.
- Jeremy's decision: keep the macro scan as a risk haircut rather than allowing it to replace company research.
- System change: added sector-sensitive uncertainty haircuts and required each candidate card to name relevant risks.
- Verification: a no-send report incorporated both scheduled and unscheduled event risk.
- Unproven: the predictive value of the haircut in future markets.

## 2026-07-30 - Delivery reliability repair

- Advice received: retry delivery of the already-rendered report without regenerating or changing the research output, and stop an interactive auto-healer from creating duplicate runs.
- Jeremy's decision: keep delivery and research separate, with no duplicate email on a failed provider attempt.
- System change: added bounded provider retry, deterministic fallback narrative, and explicit generation-versus-delivery verification.
- Verification: a no-send end-to-end run produced a report and the focused suite passed.
- Unproven: provider reliability outside the verified run.

## 2026-08-03 - Momentum-exhaustion correction and replacement decision

- Advice received: DXCM had a tangible company catalyst, but its largest positive day contributed 71% of its positive five-day move. SNOW had a specific data-cloud and AI-platform thesis. YUMC was the replacement watchlist comparison after DXCM failed the exhaustion gate.
- Jeremy's decision: keep the 60% threshold as a hard exclusion, do not use the 71% statistic as a positive signal, and treat SNOW and YUMC as watchlist or holding-state decisions subject to availability.
- System change: reject weekly replacement candidates at or above 60% largest-up-day share, invalidate stale DXCM watchlists, and keep watchlist cards distinct from trade instructions.
- Verification: the corrected report omitted DXCM from the eligible watchlist and retained the candidate availability warning.
- Unproven: whether YUMC or SNOW will outperform after the catalyst window and after execution costs.

## 2026-08-03 - Paired action invariant

- Advice received: a proposed Fidelity sale must not appear by itself.
- Jeremy's decision: require a corresponding buy or explicitly approved proceeds hold for every sale.
- System change: preserve the paired plan of SELL XLV with BUY CIBR, QQQ, and XLF in the private action renderer, with settlement required before dependent buys.
- Verification: dry-render and focused tests confirmed no unmatched sale in the reviewed plan.
- Unproven: execution and settlement until an authorized account readback confirms them.

## 2026-08-08 - SNOW added, DXCM unbought because of the trade limit

- Advice received: the prior watchlist contained SNOW and DXCM as possible individual-stock candidates, with availability requiring manual confirmation.
- Jeremy's decision: confirm SNOW was added to Cash App; do not record DXCM as held because the $150 trade limit was reached.
- System change: update the private holdings source's confirmation date and preserve SNOW as a value-pending holding while retaining DXCM as unbought.
- Verification: the canonical JSON parses, the generator reads that file as its Cash App source of truth, and the next report is expected to show SNOW as held rather than as a new candidate.
- Unproven: SNOW's cost basis, current value, sale proceeds, and realized performance.
