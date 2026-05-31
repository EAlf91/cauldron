# Research Questions (RQ.md)

These questions are extracted from [RESEARCH.md](./RESEARCH.md) and drive the daily update of [MEMORY.json](./MEMORY.json).
For each run, look up the most current publicly available data and update every matching KPI field in `MEMORY.json`, adding a new entry to the `historical` array for today's date.

---

## RQ-01 · AI-Washing & Narrative-Driven Valuation
- Have any new companies added "AI" to their name or branding in the past week without a substantive AI product or revenue stream? If so, what was the intraday stock surge (%)? Update `narrativeSurgeNewbird` (or add a new entry) with the most extreme recent example.
- What share of S&P 500 earnings calls in the latest quarter mentioned AI in "highly positive terms"? (baseline: 47 % in Q4 2025)

## RQ-02 · Circular Financing / Recursive Architecture
- What is OpenAI's current annualised revenue (USD billions)? Update `openAiRevenueBn`.
- Has the total committed infrastructure spend through 2031 changed from the $1.5 trillion baseline?
- Have any major hyperscalers (Microsoft, Amazon, Google, Meta) publicly revised their capital-expenditure guidance upward or downward?

## RQ-03 · Hyperscaler Capex
- What is the latest projected aggregate hyperscaler/data-centre capex for the current calendar year (USD billions)? Update `hyperscalerCapexBn` and its `yoyGrowth` field.
- What percentage of this capex is reported to be funded through ABS or off-balance-sheet vehicles?

## RQ-04 · Valuation Multiples
- What is today's Shiller CAPE (cyclically adjusted P/E) ratio for the U.S. stock market? Update `capeRatio.value`. (baseline: 40.0 ×; dot-com peak: 43.5 ×)
- What is the current S&P 500 Forward P/E ratio? Update `sp500ForwardPE.value`. (baseline: 23 ×; historical avg: 16 ×)
- What is the current average or range of P/E ratios for the Magnificent-7 tech stocks? Update `top7StocksPE.value`. (baseline: 22–32 ×)
- What is the current Buffett Indicator (total market cap / GDP) level?

## RQ-05 · Energy & Grid Infrastructure
- What is the current average grid connection delay (years) for large-scale data centres in major U.S. markets? Update `gridConnectionDelay.value`. (baseline: 5–7 years)
- What is the latest estimate of global data-centre electricity consumption (TWh) for 2026 and 2030? Update `dataCenterPowerDemandTWh`.
- Has the share of AI workloads in total data-centre power consumption changed? (baseline: ~21 % in 2026)

## RQ-06 · Venture Capital Dynamics
- What share (%) of total global venture investment flowed into AI in the most recent quarter? Update `vcAiConcentration.value` and its `totalVcBn` / `aiVcBn` sub-fields. (baseline: 80 %, $242 B of $300 B in Q1 2026)
- How many AI-focused companies have reached a $1 B+ valuation since 2024? Update `aiUnicornsSince2024.value`. (baseline: 207)

## RQ-07 · Regulatory & Legal Environment
- What is the latest status of FTC "Operation AI Comply"? Have new enforcement actions been filed?
- Have the SEC's AI-washing enforcement actions resulted in any settlements or judgements?
- Are there new or pending AI governance regulations (U.S. or EU) that affect market dynamics?

## RQ-08 · Productivity & Counter-Evidence
- Are there new peer-reviewed studies or large-scale surveys on AI coding-assistant productivity? Does the "19 % slower" finding hold, or has it been updated? Add relevant findings to `topStories`.
- What is the latest reported enterprise Gen AI implementation failure rate? (baseline: ~95 % in certain environments)

## RQ-09 · Sentiment & Unconventional Indicators
- What percentage of the latest quarterly S&P 500 earnings calls mentioned AI positively? (baseline: 47 % in Q4 2025)
- Are there new "God-like" leadership statements (Jensen Huang, Sam Altman, etc.) that moved markets?
- What is the current volume of "AI slop" / AI-generated content as a share of internet content? (baseline: ~90 % projected by late 2026)

## RQ-10 · Overall Heat Score
- Based on the updated KPI values above, recalculate the `heatScore` (0–100) using the existing `weight` and `score` structure in `MEMORY.json`.  
  Formula: `heatScore = round( sum(score_i) / sum(weight_i) * 100 )`
- Update `heatLabel` accordingly:
  - 80–100 → "Boiling"
  - 60–79 → "Hot"
  - 40–59 → "Warm"
  - 0–39 → "Cool"
- Append a new object to the `historical` array with today's date and the updated KPI snapshot.
- Update `lastUpdated` to today's ISO date.

---

## Output Contract

After answering the questions above, update **`MEMORY.json`** in-place with:
1. New KPI values in the `kpis` object (update `value`, `score`, and any sub-fields that changed).
2. A new entry appended to the `historical` array for today's date, while keeping at least the latest 10 days of `historical` entries in `MEMORY.json`.
3. Updated `heatScore`, `heatLabel`, `summary`, and `lastUpdated` at the root level.
4. Up to 3 new entries prepended to `topStories` for the most significant developments found. Each entry must include a `sourceUrl` field with the direct URL to the primary source article or report.

Keep at least the latest 10 days of `historical` and `topStories` entries in `MEMORY.json` at all times.  
If you need to reduce size, only trim entries older than that 10-day window (archive/fallback only).  
Do **not** change the JSON schema.
