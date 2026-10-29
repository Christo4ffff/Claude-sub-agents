# Claude sub-agents for digital marketing

Claude Code sub-agents for day-to-day work as a digital marketer. Each agent lives in `.claude/agents/` and is picked up automatically when Claude Code runs in this project.

| Agent | Use it for |
|---|---|
| `keyword-search-term-analyst` | Search term reports, negative keywords, keyword research |
| `ad-copy-reviewer` | Reviewing and rewriting ad copy (RSA, Meta, LinkedIn) with character counts |
| `landing-page-checker` | SEO analyses (nulmeting, rebuild dossier, keyword map, redirects) and landing page CRO checks |
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

- All agents inherit all tools, including connected MCP data sources such as Supermetrics, skills and Artifacts.
- Client-facing documents use the Klikfabriek house skills: `klikfabriek-offerte` for offers, `klikfabriek-report-layout` for proposals and analyses, `klikfabriek-weekrapport` for the weekly email. Documents are drafted as an Artifact first; the PDF is only rendered once the draft is approved.
- Agents never invent figures, prices or case results; they use placeholders where data is missing.
- Agents answer in the language you write in.
