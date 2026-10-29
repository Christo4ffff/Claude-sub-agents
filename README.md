# Claude sub-agents for digital marketing

Claude Code sub-agents for day-to-day work as a digital marketer. Each agent lives in `.claude/agents/` and is picked up automatically when Claude Code runs in this project.

| Agent | Use it for |
|---|---|
| `keyword-search-term-analyst` | Search term reports, negative keywords, keyword research |
| `ad-copy-reviewer` | Reviewing and rewriting ad copy (RSA, Meta, LinkedIn) with character counts |
| `landing-page-checker` | CRO audit of landing pages: message match, UX, speed, tracking |
| `weekly-client-reporter` | Weekly client performance reports across channels |
| `tracking-setup-auditor` | GA4, GTM, Google Ads/Meta conversions, Consent Mode v2 audits |
| `proposal-writer` | Proposals and quotes for new clients |

## Usage

Claude delegates automatically based on each agent's description, or you can ask for one explicitly:

```
Use the keyword-search-term-analyst to go through this search terms export.
Have the ad-copy-reviewer check these RSA headlines.
Ask the weekly-client-reporter to write last week's report for <client>.
```

## Installing for all projects

To use these agents in every project, copy them to your user-level agents folder:

```bash
mkdir -p ~/.claude/agents && cp .claude/agents/*.md ~/.claude/agents/
```

## Notes

- Agents without a `tools` line (keyword analyst, weekly reporter, tracking auditor) inherit all tools, including connected MCP data sources such as Supermetrics, so they can pull live data.
- Agents never invent figures, prices or case results; they use placeholders where data is missing.
- Agents answer in the language you write in.
