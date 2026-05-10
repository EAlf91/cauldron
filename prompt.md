# Daily update prompt

Use this prompt for daily cauldron updates:

```md
# How to update

0. check current state MEMORY.json
1. research using web-search agent and the research questions from RQ.md
2. update the MEMORY.json file with newest findings
3. update index.html and add new score to heat score over time

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
```
