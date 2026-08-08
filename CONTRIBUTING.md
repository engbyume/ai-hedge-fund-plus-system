# Contributing

Contributions should improve reproducibility, measurement integrity, safety, or clarity.

Before opening a pull request:

1. Run `python3 scripts/validate_repo.py`.
2. Explain the source and date for new factual claims.
3. Keep provider keys, private paths, raw account data, and raw prompts out of commits.
4. Add a changelog entry for behavior or policy changes.
5. Include a counterexample or failure mode when changing a screening rule.

New integrations should be optional, clearly licensed, and disabled by default. A proposal that enables external sending or live trading without an approval gate will not be accepted.
