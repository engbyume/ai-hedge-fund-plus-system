---
name: atlan-scale
description: Build and operate a personal, versioned context repository for catalyst-aware portfolio research, Kronos forecast evidence, benchmark measurement, and approval-gated reporting.
---

# Personal Atlan Scale

Use this skill when an operator wants a durable context layer around a research workflow that can be reproduced, evaluated, and changed without losing decision history.

This is a personal open implementation inspired by public context-layer and Agent Skills patterns. It is not an official Atlan skill and it does not authorize access to any account, provider, broker, email system, or scheduler.

## First-run intake

Before building a portfolio or schedule, ask for the operator's answers to these questions:

- What benchmark should be beaten? Is an investable proxy such as SPY acceptable?
- What is the exact start date and baseline state?
- Is the experiment simulated, paper, or live?
- What risk, drawdown, volatility, cash, sector, and single-position limits apply?
- Which sectors, countries, securities, or themes are prohibited or preferred?
- What are the target weights and rebalance trigger?
- What is the time horizon and failure review date?
- Which public skills, data providers, and forecast models should be installed?
- When should daily and weekly reviews run, in which timezone?
- Should the output be local-only, saved to a file, or sent through an approved provider?
- Are live trades or external sends allowed? Default to no.

If the operator does not answer, keep the value `null`, ask one question at a time, and keep all external actions disabled.

## Context-repository construction

Create a private runtime that is separate from the public repository. Maintain:

1. A source register with URL, owner, license or terms, retrieval date, role, and confidence.
2. A preference profile with benchmark, dates, cash-flow method, risk, weights, schedule, and action gates.
3. A research context with universe rules, individual catalysts, evidence, countercases, and invalidations.
4. A model registry with model, version, input date, seed, fallback, and output status.
5. An action ledger with watchlist, approval, staging, settlement, execution, and measurement states.
6. An evidence log with the operator's decision and the outcome, including failed or rejected ideas.

Use this source hierarchy: direct operator confirmation, live authorized account readback, primary company or model source, dated archived report, secondary discovery source, then forecast or sentiment output. Resolve conflicts by stating the conflict and stopping the affected action.

## Security and action gates

- Never claim a current value without a current source and retrieval date.
- Never infer that a screening spreadsheet proves platform tradeability.
- Keep separate account scopes separate.
- Never place a trade or send a message without explicit operator authorization.
- Require a no-send, no-trade dry run before an external action.
- Require settlement before a dependent buy.
- Every proposed sell must have a corresponding buy or a documented, explicitly approved proceeds hold. If not, block the plan.

## Individual-stock research gates

Research company-specific catalysts before ranking price momentum. Each candidate needs:

- catalyst type, source, date, and expected persistence
- positive evidence and what would confirm it
- a countercase and invalidation signal
- one-week, two-week, and one-month forecasts when available
- all five daily returns, green/red breadth, and late-versus-early momentum
- largest positive-day share of the positive five-day move
- insider-selling screen, sector overlap, macro risk, and platform availability

Reject a weekly replacement candidate when its largest positive day contributes 60% or more of the positive five-day move. Treat that result as momentum-exhaustion risk, even when a company catalyst is real. Apply a confidence and forecast haircut to weaker breadth or waning late-week momentum.

## Forecast model policy

Kronos is optional evidence. Record its version, inputs, seed, and missing-data behavior. Use a documented baseline if it cannot run. Never fabricate an output to fill a missing field, and never turn model confidence into trade authorization.

## Benchmark and evidence policy

Measure portfolio and benchmark over the same dates and with the same cash-flow and cost treatment. Report spread as portfolio minus benchmark. Label every result as machine-observed, user-confirmed, public-source, inference, or unverified. Do not convert a user's performance belief into a measured claim without an independently verified baseline.

## Daily output

The daily report should include data freshness, benchmark status, portfolio status, candidate catalysts, countercases, invalidations, macro risk, action state, and the next review condition. Watchlist comparisons must be visually and semantically distinct from sell instructions.
