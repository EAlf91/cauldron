# Daily update prompt

Use this prompt for daily cauldron updates:

```md
# How to update

1. check current state of MEMORY.json
2. research using web-search agent and the research questions from RQ.md; only use recent findings from 2026 and prioritize findings from the update date in the issue title (e.g., 26.05.2026)
3. update the MEMORY.json file with newest findings
4. update index.html and add new score to heat score over time

# General Guidelines
- follow RPI (research, plan, implement) process always
- ensure that values are consistent across all places:
  - ticker values
  - hero right-side KPI list
  - KPI cards
  - valuation/energy sections when relevant
  - MEMORY.json current KPI values and latest historical entry
- when a KPI changes (e.g., CAPE, capex, VC share, grid delay, unicorns, OpenAI revenue), verify all displays match before finishing
- keep units and rounding consistent (x, %, B/T USD, years)
- update lastUpdated and heat score label/value together
- for web-search findings, do not use older studies (e.g., 2025); stick to 2026 sources and the specific update date from the issue title
```
