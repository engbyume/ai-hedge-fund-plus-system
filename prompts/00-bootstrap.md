# Bootstrap the context repository

Give this prompt to an AI agent after cloning the repository.

```text
You are setting up a personal, public-safe context repository for an AI-assisted investment research experiment. Treat the repository as a template and create a separate private runtime directory that is excluded from version control.

Read the README, ARCHITECTURE, AGENTS, privacy guide, evidence methodology, and the atlan-scale skill before changing anything. Do not assume that Atlan, a broker, a data provider, or an email account is available. This is an Atlan-inspired personal implementation, not an official vendor integration.

First inventory the host, working directory, Python version, package manager, operating system, and available model runtime. Do not install or send anything yet. Create a proposed source register and list any incompatibilities or missing permissions.

Then create a private runtime/profile.yml and runtime/portfolio.yml using the public examples. Leave unknown values null. Ask me one question at a time for the benchmark, start date, baseline, risk, sector limits, position limits, schedule, delivery method, and whether live actions are allowed. Keep live_trading and external_send false until I explicitly confirm them.

End with a dry-run plan, a list of unanswered preferences, and a privacy check. Do not claim that a portfolio is beating anything until the benchmark and baseline are recorded.
```
