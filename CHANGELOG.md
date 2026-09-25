# Changelog

## Unreleased

### 2026-09-25 - Price refresh coverage gate

- Appended 9,702 fixed-cohort bars through the 2026-09-24 session and verified SQLite integrity.
- Recorded incomplete September 22 coverage and a same-provider retry that added no rows. Deferred aligned feature-cache rebuilding and selector replay because the full daily boundary is not yet verified.
- No prediction-accuracy claim, candidate promotion, trade, broker write, email send, or scheduler change was made.
- Reran a direct no-send report preview after delivery-gate hardening. It recorded `previewed`, zero delivery attempts, and zero proposed orders; live delivery remains blocked while model-card Cash App availability is unverified. Thirty-six focused tests and both wrapper syntax checks passed.
- Audited no-cost historical-data options and the existing September 22 Yahoo path. Thirty-two saved retry slices covered 3,154 symbols; 243 were returned and zero new bars were inserted. A fresh 20-symbol missing-data sample returned no bars, while five existing-data controls returned five bars. These bounded samples do not prove all missing symbols lack data.
- Official documentation identifies Alpaca Basic as a possible free historical SIP source for data older than 15 minutes, but it requires authenticated access. Tiingo's free plan is limited to 500 unique symbols per month, and Alpha Vantage's free service to 25 requests per day. No new account, authenticated request, or paid API call occurred.
- Rematerialized the dated historical-universe store from the main price store only after manifest and full old-row parity checks passed. The refreshed store passes integrity with 2,106,844 bars through September 24; all 2,040,294 prior rows match exactly and 66,550 rows were added. The September 22 gap remains, so no feature rebuild or replay was run.

### 2026-09-22 - Historical feasibility and no-send automation hardening

- Defined and published the exact-pair hit-rate metric separately from portfolio returns. On the shared 106-window baseline slice, no tested route improved on protected v14.
- Recorded the current decision feasibility ceiling: 89 of 111 decisions, with growth-like and transition maximum feasible runs below five.
- Made report archives record preview, provider acknowledgement, or failure. A dry run now leaves the same-day dispatch marker unchanged and skips failure email and auto-heal state changes.
- Verified a no-send report preview with zero proposed actions. No live email, trade, broker write, scheduler mutation, or model promotion occurred in this verification.
- At the time of this no-send verification, external delivery had no AgentMail sent-label readback; a later read-only check is recorded in the following entry.

### 2026-09-22 - Read-only AgentMail status verification

- A read-only metadata lookup found one `sent`-labeled report at the same time as the stored 20:31 report archive, with the configured recipient matching.
- The message body was not retrieved, so exact content matching remains unverified. No email was sent by this task.

### 2026-08-08 - Public repository bootstrap

- Created the personal `ai-hedge-fund-plus-system` publication layer.
- Added an Atlan-inspired context-repository architecture without claiming Atlan affiliation.
- Added links for Agent Skills, Kronos, the upstream AI Hedge Fund project, and the market-data, broker-readback, and delivery providers used by the private runtime.
- Added preference-driven replication prompts, a portable skill, example configuration, evidence methodology, and publication audits.
- Recorded the current Cash App decision as redacted operator evidence: SNOW was added, while DXCM was not purchased because the $150 trade limit was reached.
- Preserved the rule that no sale may appear without a corresponding buy or an explicitly documented proceeds hold.

### 2026-08-10 - Daily benchmark and candidate gates

- Made daily, five-session, monthly, and open-position all-time benchmark comparisons use current market-close data instead of a stale user-confirmed daily percentage.
- Added a pending Fidelity funding record that is excluded from buying power until the operator confirms arrival.
- Enforced three ETF-only 04A cards, including standalone held-ETF reviews when no replacement gate fails.
- Enforced two daily 04B individual-stock cards, with one SNOW replacement and one future-add candidate that both beat SNOW's current forecasts and clear catalyst and momentum-exhaustion gates.
- Removed the obsolete model references and retained Kronos as the sole forecast-model link.

## Change-log practice

Every future system change should include its date, the advice or evidence that motivated it, the operator's decision, the files or rules changed, and the verification result. Failed ideas remain in the log with their failure condition.
