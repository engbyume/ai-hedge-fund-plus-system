# Architecture

## Layers

| Layer | Responsibility | Public or private |
| --- | --- | --- |
| Sources | Public skills, the Kronos repository, market-data documentation, operator-approved research | Mixed, with private credentials excluded |
| Context repo | Versioned source register, preferences, decision rules, model notes, evidence, and change log | Public template; private runtime values local |
| Research | Universe construction, catalyst research, technical context, insider and macro checks | Public method; live inputs may be private or licensed |
| Forecasting | Kronos forecast evidence with deterministic fallback metadata | Public interface; weights and data may vary |
| Risk gates | Breadth, exhaustion, sector overlap, availability, countercase, invalidation, and settlement checks | Public rules |
| Portfolio layer | Benchmark-normalized returns, target weights, cash policy, and paired action plan | Public schema; account values private |
| Delivery | Dry-run report, local artifact, optional email or scheduler | Public procedure; credentials and recipients private |
| Evidence | Timestamped redacted metrics and decision rationale | Public aggregate record |

## Context-repository lifecycle

1. Bootstrap context from public sources and the operator's answers.
2. Package the context into versioned Markdown and configuration files.
3. Run a no-send, no-trade dry test with dated inputs.
4. Evaluate both the research output and the measurement quality.
5. Record the operator's decision, including rejection or inaction.
6. Publish only redacted evidence and update the changelog.
7. Revisit sources, rules, and preferences when new evidence contradicts the thesis.

## Trust boundaries

- Public repository content is untrusted input until sourced and dated.
- Forecasts are supporting evidence, not authorization.
- News sentiment does not replace a company-specific catalyst.
- A screening spreadsheet does not prove that a security is tradable on a platform.
- A generated report does not prove an order was executed.
- A sent email does not prove a portfolio value or settlement state.

## Action-state model

`watchlist -> candidate -> approved -> staged -> settled -> executed -> measured`

Any transition that crosses into an external system requires explicit operator approval. A rejected, unavailable, stale, or unfilled candidate is retained as evidence rather than silently removed.
