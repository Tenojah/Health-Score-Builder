# Health Score Builder

A CS Lab tool: weight your customer health indicators, spot at-risk accounts and get the recommended playbook.

## How it works

- Score = weighted average of 5 indicators (usage, adoption, NPS/CSAT, tickets, executive sponsor engagement), from 0 to 100.
- Adjustable thresholds: red below 60, green at 80 or above (defaults).
- The main factor is the indicator with the highest weight multiplied by its gap to 100.
- Playbooks are rule-based (status and main factor).
- Demo data is fictional.

## CSV import

Required columns: `account, arr, usage, adoption, nps, tickets, sponsor` (scores from 0 to 100).
Optional columns: `tier, score_30j` (score 30 days ago). Comma or semicolon separator. 1 MB and 2,000 rows maximum.
A template can be downloaded from the tool.

## Privacy

All calculation happens in the browser. No data is sent to a server, and the CSP in `netlify.toml` blocks outgoing connections.

## Deployment

Static site, no build step: publish the folder as is on Netlify (drag and drop or Git repository, publish directory `.`).
