# Public tools and integrations

The links below are references or optional integrations. They do not grant this repository permission to download, authenticate, send, trade, or scrape anything. Check each project's current license and terms before use.

| Tool or source | Link | Role | Status |
| --- | --- | --- | --- |
| Agent Skills | https://agentskills.io/ | Portable `SKILL.md` format and progressive disclosure | Required reference |
| GitHub Agent Skills | https://docs.github.com/en/copilot/concepts/agents/about-agent-skills | Host-specific skill guidance | Reference |
| Atlan docs | https://docs.atlan.com/get-started/what-is-atlan | Context-layer inspiration | Public reference |
| Atlan context scaling | https://atlan.com/know/ai-agent/how-to-scale-agent-context-layer/ | Context repository, evaluation, and trace concepts | Public reference |
| Atlan skills vs MCP | https://atlan.com/know/ai-agent/ai-agent-skills/agent-skills-vs-mcp/ | Boundary between instructions and tool protocols | Public reference |
| Chronos repository | https://github.com/amazon-science/chronos-forecasting | General time-series foundation model | Optional |
| Chronos paper | https://arxiv.org/abs/2403.07815 | Primary model reference | Public reference |
| TimesFM repository | https://github.com/google-research/timesfm | Time-series foundation model | Optional |
| Kronos repository | https://github.com/shiyu-coder/Kronos | Financial K-line forecasting | Optional |
| Upstream AI Hedge Fund | https://github.com/virattt/ai-hedge-fund | Public research-agent reference | Optional reference |
| yfinance | https://github.com/ranaroussi/yfinance | Optional public market-data adapter | Optional |
| SnapTrade | https://snaptrade.com/ | Optional broker readback | Disabled by default |
| AgentMail | https://agentmail.to/ | Optional report delivery | Disabled by default |
| GitHub Actions | https://docs.github.com/en/actions | Optional public validation schedule | Optional |

## Installation policy

The replication prompts must inspect the host before installing. Install only compatible components, keep optional models behind a feature flag, record versions, and provide a deterministic fallback. Never place keys in this file or in a public configuration example.
