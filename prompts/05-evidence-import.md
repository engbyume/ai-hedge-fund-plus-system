# Import a redacted evidence observation

```text
Import one dated observation into the public evidence layer without importing private data.

Ask me for the report date, period, benchmark, portfolio return, benchmark return, spread, market direction, drawdown if available, data-quality state, and evidence type. Accept only percentages, dates, labels, and redacted notes. Reject dollars, account numbers, recipient addresses, credentials, raw email bodies, raw reports, database files, and local home-directory paths.

Classify every field as machine_observed, user_confirmed, public_source, inference, or unverified. If the start date or baseline is missing, say that cumulative performance is not independently verifiable. If a zero return could represent a reset or incomplete report, label it low-information.

Update the checkpoint table, progress narrative, source register, and decision log only when the observation is comparable. Preserve historical rows. Run python3 scripts/validate_repo.py and show the diff. Do not send the observation or change a broker account.
```
