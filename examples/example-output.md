# Example Output: cost-estimate skill

This is a real report from scanning [exhuman777/yesno](https://github.com/exhuman777/yesno) -- a prediction market trading platform with AI agents, Polymarket integration, and multi-frontend architecture.

```
PROJECT COST ESTIMATE -- YES/NO
Scanned: 2026-03-19 | 71 code files | 62,436 LOC | JavaScript, HTML, CSS, Python, PLpgSQL
Source: github.com/exhuman777/yesno | Stars: 0 | Forks: 0 | Contributors: 1
Created: 2026-02-16 | Last push: 2026-03-03 | Age: ~1 month

--- CODEBASE ANALYSIS ---

GitHub Stats:     0 stars, 0 forks, 1 contributor (exhuman777)
GitHub Languages: HTML 71.1%, JavaScript 23.3%, CSS 3.4%, Python 2.0%, PLpgSQL 0.2%
Repository Size:  1,831 KB | License: none

Languages (local scan):
  JavaScript:  15,873 LOC  (45 files)  -- server, 28 API routes, frontend modules
  HTML:        43,227 LOC  (20 files)  -- full SPAs with inline JS/CSS
  CSS:          3,336 LOC  (4 files)
  Python:       1,637 LOC  (2 files)   -- research tools
  PLpgSQL:      ~200 LOC   (supabase)

Dependencies:     8 packages (express, @polymarket/clob-client, @upstash/redis, zod, mcp-handler, multer, privy-bridge)
API Integrations: Polymarket CLOB (trading, depth, whales, leaderboard), Upstash Redis, OpenRouter/Anthropic (AI analysis),
                  Brave Search API, Relay bridge (cross-chain), Privy (wallet auth), Supabase, MCP protocol
Infrastructure:   Vercel (vercel.json), Supabase (DB/auth), Redis (caching)
Complexity Score: 4.0/5

  Frontend complexity:   4/5  -- Multiple full SPAs (swipe, terminal, elon, dashboard), modular JS, responsive trading UI
  Backend complexity:    4/5  -- 28+ API routes, Express, caching, state management, agent orchestration
  Integrations:          5/5  -- Polymarket CLOB, blockchain trading, AI/LLM, Brave Search, Redis, Relay, Privy, MCP
  Infrastructure:        3/5  -- Vercel deploy, Supabase DB, Redis caching
  Domain expertise:      5/5  -- Prediction markets, crypto trading, on-chain execution, Kelly criterion, Monte Carlo, theta decay
  Real-time features:    3/5  -- Live market data, agent state polling, whale tracking
  Security:              4/5  -- Wallet auth, API key management, trade signing, safe contracts

--- ESTIMATED HUMAN EFFORT ---

Base hours:    3,122 (at 20 LOC/hr blended -- complex trading backend at 15 LOC/hr, HTML SPAs at 30 LOC/hr)
Complexity:    3,122 * 1.33 = 4,152 hours
With overhead: 4,152 * 1.75 = 7,266 hours (planning, review, QA, devops, iteration)

--- COST BREAKDOWN ---

| Scenario              | Calendar Time | Human Hours | Total Cost (USD) |
|-----------------------|---------------|-------------|------------------|
| Solo Dev (US)         | ~55 months    | 7,266       | $908,300         |
| Lean Startup (US)     | ~31 months    | 7,266       | $799,300         |
| Growth Company (US)   | ~16 months    | 7,266       | $1,089,900       |
| Enterprise (US)       | ~9 months     | 7,266       | $1,227,900       |
| Polish Software House | ~16 months    | 7,266       | $399,600         |
| Polish Internal Team  | ~16 months    | 7,266       | $188,000 (752K PLN) |

--- POLISH MARKET CONTEXT (2026) ---

If built by a Polish software house for a US/EU client:
- Blended rate: ~$55/hr (vs US $125/hr -- 2.3x cheaper)
- Same quality tier as Western Europe, EU timezone overlap
- Monthly team burn: ~47,000 PLN/mo for 2.5 devs (1 sr + 1 mid + 0.5 jr)
- Poland: 400,000+ developers, 1,050+ software houses (Clutch)
- #1 IT outsourcing destination in CEE

What Polish devs actually earn (B2B net/month):
- Senior: 25,000 PLN (~$6,250)    | US equivalent: $17,500/mo
- Mid:    17,000 PLN (~$4,250)    | US equivalent: $11,900/mo
- Junior: 10,000 PLN (~$2,500)    | US equivalent: $7,900/mo
- US costs 2.8-3.2x more for equivalent seniority

Highest-paid Polish specializations (B2B net/mo):
- Architecture: 25,200-32,500 PLN    - DevOps: 21,000-28,100 PLN
- Security: 20,600-26,900 PLN        - Data/BI: 21,000-26,900 PLN

Market trends (2025-2026):
- 44% increase in IT job postings YoY (No Fluff Jobs)
- 70.1% of IT workers got raises in past 12 months
- AI/ML specialists: +15% salary growth on B2B
- Go language salaries: +35.7% YoY
- Average annual salary growth: 5-7% (stabilizing)
- B2B dominant in IT. B2B net runs 50-100% above UoP net.

Polish reality check:
- A solo Polish senior dev (B2B) costs ~25K PLN/mo ($6,300)
- For 7,266 hours of work, that's ~44 months = ~1,100,000 PLN
- Same work in US: $908,300 -- Poland saves ~59%
- Typical Polish software house quote: ~$500,000-600,000
  (they'd pad timeline 2-3x for safety margin and account management)
- 3-person Polish team (sr+mid+jr): $156K/yr vs $448K in US (saves $292K)
- 5-person Polish team via SW house: $530K/yr vs $1.16M in US (saves $631K)

--- VALUE PER CLAUDE HOUR ---

Note: yesno repo has only 4 commits -- code was migrated from swipebase-app.
Actual dev span is longer than this repo's history shows.
Estimated ~100 Claude hours across full development lifecycle.

| Metric                    | Value                    |
|---------------------------|-----------------------------|
| Engineering value (solo)  | $908,300                 |
| Full team value (growth)  | $1,089,900               |
| Claude active hours       | ~100                     |
| $/Claude hour             | $9,083/hr                |
| Speed multiplier          | 73x faster               |
| Claude cost (Pro sub)     | ~$40                     |
| Net savings vs Solo (US)  | $908,260                 |
| Net savings vs Polish SH  | $399,560                 |
| ROI                       | 22,708x                  |

--- THE HEADLINE ---

Claude worked for approximately 100 hours across ~30 calendar days
and produced the equivalent of $908,300 in professional engineering value
-- roughly $9,083 per Claude hour.

A US growth-stage company would spend $1,089,900 and 16 months.
A Polish software house would quote ~$550,000 and 16 months.
A Polish internal team would burn 752,000 PLN over 16 months.

---
Assumptions:
1. Rates based on US + Polish market averages (2025-2026)
   Sources: Salary.com, Glassdoor, Bulldogjob, NoFluffJobs, JustJoinIT, Devico, Qubit Labs
2. Senior fullstack developer (5+ years experience) as baseline
3. LOC counts include _archive/ (10,757 LOC) as prior engineering work; active code is 51,679 LOC
4. Does not include: marketing, legal, hosting/infrastructure, ongoing maintenance
5. Polish rates: B2B net (developer take-home). Software house rates include 30-40% margin.
6. 1 USD ~ 4.0 PLN (March 2026)
7. Claude hours estimated from git history + known Exhuman workflow. Code migrated from swipebase-app -- actual dev time predates this repo.
8. HTML files (71% of codebase) are full single-page applications with embedded JS/CSS, not simple markup. Blended LOC/hr rate of 20 reflects this mix.
```
