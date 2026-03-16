# Example Output: cost-estimate skill

This is a sample report from scanning a mid-sized Next.js web application.

```
PROJECT COST ESTIMATE -- acme-dashboard
Scanned: 2026-03-16 | 127 files | 14,280 LOC | TypeScript, CSS, Python
Source: github.com/acme/dashboard | Stars: 342 | Forks: 28 | Contributors: 5
Created: 2025-06-12 | Last push: 2026-03-14 | Age: 9 months

--- CODEBASE ANALYSIS ---

GitHub Stats:     342 stars, 28 forks, 5 contributors
GitHub Languages: TypeScript 72.3%, CSS 14.1%, Python 8.6%, JavaScript 3.2%, Other 1.8%
Repository Size:  4,820 KB | License: MIT

Languages:        TypeScript (89 files, 10,200 LOC), CSS (18 files, 2,100 LOC),
                  Python (12 files, 1,500 LOC), JavaScript (8 files, 480 LOC)
Dependencies:     47 packages (34 deps + 13 devDeps)
API Integrations: Supabase, Stripe, OpenAI, Resend
Infrastructure:   Vercel (vercel.json), GitHub Actions (2 workflows)
Complexity Score: 3.4/5

--- ESTIMATED HUMAN EFFORT ---

Base hours:    571 (at 25 LOC/hr avg -- standard web app with integrations)
With overhead: 1,000 hours (planning, review, QA, devops, iteration)

--- COST BREAKDOWN ---

| Scenario              | Calendar Time | Human Hours | Total Cost (USD) |
|-----------------------|---------------|-------------|------------------|
| Solo Dev (US)         | ~7.6 mo       | 1,000       | $125,000         |
| Lean Startup (US)     | ~5.1 mo       | 1,000       | $110,000         |
| Growth Company (US)   | ~3.0 mo       | 1,000       | $125,000         |
| Enterprise (US)       | ~2.5 mo       | 1,000       | $169,000         |
| Polish Software House | ~3.0 mo       | 1,000       | $55,000          |
| Polish Internal Team  | ~3.0 mo       | 1,000       | $42,000 (168,000 PLN) |

--- POLISH MARKET CONTEXT (2026) ---

If built by a Polish software house for a US/EU client:
- Blended rate: ~$55/hr (vs US $125/hr -- 2.3x cheaper)
- Same quality tier as Western Europe, EU timezone overlap
- Monthly team burn: ~56,000 PLN/mo for 3 devs
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
- For 1,000 hours of work, that's ~6.1 months = ~152,500 PLN
- Same work in US: $125,000 -- Poland saves ~56%
- Typical Polish software house quote for this project: $72,000
  (they'd pad timeline 2-3x for safety margin and account management)
- 3-person Polish team (sr+mid+jr): $156K/yr vs $448K in US (saves $292K)
- 5-person Polish team via SW house: $530K/yr vs $1.16M in US (saves $631K)

--- VALUE PER CLAUDE HOUR ---

| Metric                    | Value                    |
|---------------------------|--------------------------|
| Engineering value (avg)   | $125,000                 |
| Full team value (growth)  | $125,000                 |
| Claude active hours       | 38                       |
| $/Claude hour             | $3,289/hr                |
| Speed multiplier          | 26x faster               |
| Claude cost (Pro sub)     | ~$47                     |
| Net savings vs Solo (US)  | $124,953                 |
| Net savings vs Polish SH  | $54,953                  |
| ROI                       | 2,659x                   |

--- THE HEADLINE ---

Claude worked for approximately 38 hours across 14 calendar days
and produced the equivalent of $125,000 in professional engineering value
-- roughly $3,289 per Claude hour.

A US growth-stage company would spend $125,000 and 3 months.
A Polish software house would quote $72,000 and 3 months.
A Polish internal team would burn 168,000 PLN over 3 months.

---
Assumptions:
1. Rates based on US + Polish market averages (2025-2026)
   Sources: Salary.com, Glassdoor, Bulldogjob, NoFluffJobs, JustJoinIT, Devico, Qubit Labs
2. Senior fullstack developer (5+ years experience) as baseline
3. Testing estimated at 20% of effort (no dedicated test suite detected)
4. Does not include: marketing, legal, hosting/infrastructure, ongoing maintenance
5. Polish rates: B2B net (developer take-home). Software house rates include 30-40% margin.
6. 1 USD ~ 4.0 PLN (March 2026)
```
