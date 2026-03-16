```
 ██████╗ ██████╗ ███████╗████████╗
██╔════╝██╔═══██╗██╔════╝╚══██╔══╝
██║     ██║   ██║███████╗   ██║
██║     ██║   ██║╚════██║   ██║
╚██████╗╚██████╔╝███████║   ██║
 ╚═════╝ ╚═════╝ ╚══════╝   ╚═╝
███████╗███████╗████████╗██╗███╗   ███╗ █████╗ ████████╗███████╗
██╔════╝██╔════╝╚══██╔══╝██║████╗ ████║██╔══██╗╚══██╔══╝██╔════╝
█████╗  ███████╗   ██║   ██║██╔████╔██║███████║   ██║   █████╗
██╔══╝  ╚════██║   ██║   ██║██║╚██╔╝██║██╔══██║   ██║   ██╔══╝
███████╗███████║   ██║   ██║██║ ╚═╝ ██║██║  ██║   ██║   ███████╗
╚══════╝╚══════╝   ╚═╝   ╚═╝╚═╝     ╚═╝╚═╝  ╚═╝   ╚═╝   ╚══════╝
```

<p align="center">
  <strong>Codebase Value Calculator for Claude Code</strong>
</p>

<p align="center">
  <em>Point it at any GitHub repo or local directory. Get a full cost breakdown in seconds.</em>
</p>

<p align="center">
  <a href="#how-it-works">How it Works</a> &middot;
  <a href="#methodology">Methodology</a> &middot;
  <a href="#rate-data">Rate Data</a> &middot;
  <a href="#why-polish-rates">Why Polish Rates</a> &middot;
  <a href="#install">Install</a> &middot;
  <a href="#example-output">Example</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/type-Claude_Code_Skill-orange" alt="Skill" />
  <img src="https://img.shields.io/badge/input-GitHub_URL_or_Local-black" alt="Input" />
  <img src="https://img.shields.io/badge/data-2025--2026_Market_Rates-amber" alt="Rates" />
  <img src="https://img.shields.io/badge/license-MIT-green" alt="MIT" />
</p>

---

## What This Is

A Claude Code skill that answers: **"What would this cost to build with a real team?"**

You give it a codebase. It scans everything -- lines of code, languages, dependencies, API integrations, infrastructure configs, git history. Then it estimates human effort, calculates costs across 6 team scenarios (US and Polish markets), and shows you the ROI of building with Claude instead.

Works on any public GitHub repo or any local directory on your machine.

```
/cost-estimate github.com/vercel/next.js
/cost-estimate https://github.com/shadcn-ui/ui
/cost-estimate ~/projects/my-app
/cost-estimate
```

---

## How it Works

```
                    INPUT
                      |
          +-----------+-----------+
          |                       |
    GitHub URL              Local Path
          |                       |
    shallow clone            use directly
    gh api metadata               |
          |                       |
          +-----------+-----------+
                      |
               SCAN CODEBASE
          (LOC, files, deps, APIs,
           infra, contracts, git)
                      |
              SCORE COMPLEXITY
          (7 factors, each 1-5)
                      |
            ESTIMATE HUMAN HOURS
          (LOC / productivity rate
           x complexity x 1.75)
                      |
          CALCULATE COST x 6 TEAMS
          (Solo, Startup, Growth,
           Enterprise, Polish SH,
           Polish Internal)
                      |
           CALCULATE CLAUDE ROI
          (speed, savings, $/hour)
                      |
                   REPORT
```

### Step-by-step

**1. Parse input.** Detect if the argument is a GitHub URL or local path. If GitHub, shallow-clone to `/tmp/` and pull repo metadata via `gh api` (stars, forks, contributors, languages, age, license, latest commit).

**2. Scan.** Count lines of code across 17 file extensions. Exclude build artifacts (`node_modules`, `.next`, `dist`, `build`, `vendor`, `__pycache__`). Detect `package.json` / `requirements.txt` / `Cargo.toml` / `go.mod` for dependencies. Grep for API integrations (Supabase, Stripe, OpenAI, etc.). Find infrastructure configs (Vercel, Railway, Docker, GitHub Actions). Detect Solidity contracts.

**3. Score complexity.** Seven factors, each scored 1-5:

| Factor | What gets scored |
|--------|-----------------|
| Frontend complexity | Components, state management, animations, responsive design |
| Backend complexity | API routes, middleware, auth, DB schemas, cron jobs |
| Integrations | Third-party APIs, payments, blockchain, AI/LLM calls |
| Infrastructure | CI/CD, deployment configs, multi-environment, caching |
| Domain expertise | Specialized knowledge (trading, crypto, ML, compliance) |
| Real-time features | WebSockets, SSE, polling, live data feeds |
| Security | Auth flows, encryption, key management, OWASP surface |

**4. Estimate hours.** Base hours = LOC / productivity rate. Productivity rates vary by complexity tier:

```
Simple CRUD / static pages:       40-60 LOC/hr
Standard web app:                 20-35 LOC/hr
Complex integrations / trading:   10-20 LOC/hr
Smart contracts / security-critical: 5-15 LOC/hr
```

Multiply by complexity factor (average score / 3). Then apply 1.75x overhead multiplier for the stuff that isn't writing code:

```
Project setup, architecture:  +15%
Code review, QA, testing:     +20%
DevOps, deployment:           +10%
Meetings, docs, communication: +15%
Bug fixes, iterations:        +15%
                              -----
Total overhead:               1.75x
```

**5. Calculate costs.** Six team scenarios, each with different composition and blended rate. Same hours, different burn rates and calendar times.

**6. Calculate AI comparison.** Estimate Claude hours from git log (commits x 0.25 hrs avg). Compute speed multiplier, cost savings, ROI, and value per Claude hour.

**7. Clean up.** If a GitHub repo was cloned, delete the temp directory.

---

## Methodology

### Why These Numbers Aren't Bullshit

Every estimation tool has assumptions baked in. Here's what ours are and why they hold up.

### LOC as a proxy for effort

LOC is a famously imperfect metric. But it's not useless. The key insight: **LOC correlates with effort when you control for complexity.** A 10,000-line CRUD app and a 10,000-line trading system are wildly different projects. That's why we don't just divide LOC by a flat rate. We score 7 complexity factors independently and use them as a multiplier.

The productivity rates (20-35 LOC/hr for standard web apps) come from industry benchmarks that account for thinking time, debugging, refactoring, and testing -- not just typing speed. A senior developer writing 25 lines of tested, production-quality code per hour is well within published norms (McConnell's "Code Complete", COCOMO II, industry surveys).

### The 1.75x overhead multiplier

Writing code is roughly 57% of a software project. The rest:

- **Architecture and planning (15%)** -- You don't start typing on day one. Someone has to decide the stack, design the schema, plan the API, set up the repo. Even on solo projects, this is real time.
- **Code review and QA (20%)** -- In a team setting, every PR gets reviewed. QA catches things the developer missed. Even solo devs spend time testing their own work.
- **DevOps (10%)** -- CI/CD pipelines, deployment configs, monitoring setup, SSL certs, DNS, environment variables. The "it works on my machine" to "it works in production" gap.
- **Communication (15%)** -- Standups, Slack, email, documentation, onboarding, spec clarification. Solo devs skip some of this, teams don't.
- **Bug fixes and iterations (15%)** -- First version is never the last. Stakeholder feedback, edge cases, performance issues, compatibility bugs.

1.75x is actually conservative. Most enterprise estimates use 2.0-3.0x. We use 1.75x because Claude Code projects tend to have less communication overhead and faster iteration cycles.

### The 6 scenarios

Different team compositions exist because software development economics vary dramatically by context:

**Solo Dev (US, $125/hr)** -- One senior fullstack developer. Realistic floor for a US freelancer with 5+ years experience. Calendar time is long because one person can only do 6 productive hours per day, 22 days per month.

**Lean Startup (US, $110/hr blended)** -- 1 senior fullstack + 0.5 mid frontend + 0.25 DevOps. Typical early-stage team. Slightly faster calendar time because work parallelizes.

**Growth Company (US, $125/hr blended)** -- 1 lead + 1 senior backend + 1 mid frontend + 0.5 DevOps + 0.25 designer + PM overhead (20%). This is what a Series A/B company actually looks like. PM overhead is real -- someone has to manage tickets, write specs, run retros.

**Enterprise (US, $130/hr + 30% overhead)** -- Full team with QA, dedicated DevOps, PM, designer. The 30% overhead covers compliance, security reviews, change management, procurement processes, and the 3 meetings it takes to approve a button color.

**Polish Software House ($55/hr blended)** -- Same team as Growth Company, Polish rates. This is the client-facing rate -- what a US/EU company pays when outsourcing to Poland. The software house takes a 30-40% margin on top of developer cost.

**Polish Internal Team (PLN)** -- Hiring developers directly in Poland on B2B or UoP contracts. Monthly burn rate in PLN. Cheapest option if you have the local presence to manage the team.

### Why the AI comparison matters

The AI comparison section isn't just feel-good numbers. It answers a legitimate business question: **"What did I actually get for my Claude subscription?"**

We estimate Claude hours from git history (commits x 0.25 hours average). This is conservative -- some commits take 5 minutes, some take an hour. The 15-minute average accounts for the fact that AI-assisted development produces more commits per unit of meaningful work (smaller, more atomic changes).

The ROI calculation compares Claude cost (Pro subscription prorated by active days) against what the same output would cost at market rates. This isn't hypothetical -- the code exists, it works, and we can measure its complexity.

---

## Rate Data

### Sources

All rates are verified against multiple sources. Nothing is made up.

**US rates:**
- Salary.com (2025-2026 compensation data)
- Glassdoor (salary reports with location adjustment)
- Robert Half Technology Salary Guide
- Levels.fyi (for senior/lead calibration)
- Arc.dev and Toptal rate surveys (for freelancer rates)

**Polish rates:**
- **Bulldogjob IT Community Report 2025** -- 4,800 respondents, the gold standard for Polish IT salary data
- **JustJoinIT 2026** -- 111,000+ job postings analyzed, largest Polish IT job board
- **NoFluffJobs** -- salary transparency platform, all listings show rates
- **Devico** -- Polish outsourcing market analysis
- **Qubit Labs** -- Eastern European developer cost benchmarks

**Exchange rate:** 1 USD ~ 4.0 PLN (March 2026)

### US Market Rates (hourly, fully loaded)

| Role | Junior | Mid | Senior | Lead/Architect |
|------|--------|-----|--------|----------------|
| Fullstack | $55 | $85 | $125 | $165 |
| Frontend | $50 | $80 | $120 | $155 |
| Backend | $55 | $85 | $130 | $170 |
| DevOps | $60 | $90 | $135 | $175 |
| Smart Contract | $70 | $110 | $160 | $200 |
| Designer | $45 | $70 | $100 | $130 |

"Fully loaded" means the rate includes employer taxes, benefits, equipment, office space, and management overhead. This is what the company actually pays per hour of developer time, not take-home pay.

### Polish Market Rates (hourly, B2B client-facing)

| Role | Junior | Mid | Senior | Lead/Architect |
|------|--------|-----|--------|----------------|
| Fullstack | $25 | $42 | $70 | $90 |
| Frontend | $22 | $38 | $65 | $85 |
| Backend | $25 | $42 | $65 | $88 |
| DevOps | $28 | $45 | $70 | $95 |
| Smart Contract | $30 | $55 | $85 | $110 |
| Designer | $20 | $35 | $55 | $70 |

These are what a US/EU client pays a Polish software house per developer hour. The house takes 30-40% margin. The developer sees less.

### What Polish Developers Actually Earn

Monthly B2B net (what the developer invoices):

| Role | Junior | Mid | Senior | Lead |
|------|--------|-----|--------|------|
| Frontend | ~7,950 PLN | ~17,640 PLN | ~23,520 PLN | ~27,000 PLN |
| Backend | ~10,125 PLN | ~20,180 PLN | ~25,350 PLN | ~27,000 PLN |
| Fullstack | ~6,600 PLN | ~17,000 PLN | ~24,300 PLN | ~27,000 PLN |
| DevOps | ~10,790 PLN | ~22,000 PLN | ~26,650 PLN | ~28,500 PLN |

Employment contract (UoP gross/month -- employer pays ~40% more on top for ZUS, taxes):

| Role | Junior | Mid | Senior |
|------|--------|-----|--------|
| Frontend | ~9,500 PLN | ~15,500 PLN | ~21,950 PLN |
| Backend | ~8,625 PLN | ~16,550 PLN | ~23,370 PLN |
| Fullstack | ~8,200 PLN | ~13,700 PLN | ~19,900 PLN |

### US vs Poland Direct Comparison (annual total cost)

| Seniority | Poland (B2B) | US (FTE all-in) | US costs X more |
|-----------|-------------|-----------------|-----------------|
| Junior | $30,000 | $95,000 | 3.2x |
| Mid | $51,000 | $143,000 | 2.8x |
| Senior | $75,000 | $210,000 | 2.8x |
| Lead | $81,000 | $250,000 | 3.1x |

---

## Why Polish Rates

Not because it's exotic. Because it's the most useful comparison point for real decision-making.

**Poland is the #1 IT outsourcing destination in Central and Eastern Europe.** 400,000+ developers, 1,050+ software houses listed on Clutch. Same timezone overlap as Western Europe. EU member state. English proficiency above European average. Major delivery centers in Warsaw, Krakow, Wroclaw, Gdansk, Poznan.

When a US startup asks "should we outsource?", Poland is almost always on the shortlist alongside Ukraine, Romania, and India. But Poland has a unique combination: EU legal protections, strong IP law, no timezone pain for European clients, and quality that benchmarks against Western Europe at 2.8-3.2x lower cost.

The Polish market data in this skill comes from **real salary surveys with real sample sizes** -- not from outsourcing marketing pages. Bulldogjob surveys 4,800+ IT professionals annually. JustJoinIT analyzes 111,000+ actual job postings. NoFluffJobs requires salary transparency on every listing. This is the kind of data that Polish developers themselves use to negotiate their contracts.

### B2B vs UoP: Why It Matters

Poland has two dominant employment models in IT:

- **B2B (jednoosobowa dzialalnosc gospodarcza)** -- Self-employment. Developer invoices the company monthly. Higher net pay, fewer protections, developer handles their own taxes and insurance. Dominant in IT (especially senior roles).
- **UoP (umowa o prace)** -- Employment contract. Lower net pay, but employer handles taxes, ZUS contributions, paid leave, and provides labor protections. Employer cost is ~40% above gross salary.

This distinction matters because the "cost" of a Polish developer depends entirely on which model you're using. A senior fullstack on B2B nets ~24,300 PLN/mo. The same developer on UoP grosses ~19,900 PLN but costs the employer ~27,860 PLN when you add mandatory contributions.

Software houses almost exclusively use B2B. Direct hires vary -- juniors often start on UoP, seniors prefer B2B for the tax efficiency.

### Market Trends (2025-2026)

- 44% increase in IT job postings YoY (No Fluff Jobs)
- 70.1% of IT workers got raises in past 12 months
- AI/ML specialists: +15% salary growth on B2B
- Go language salaries: +35.7% YoY (fastest growing)
- Average annual salary growth: 5-7% (stabilizing after post-COVID volatility)
- B2B dominant in IT. B2B net runs 50-100% above UoP net at same seniority
- Highest-paid specializations (B2B net/mo): Architecture (25,200-32,500 PLN), DevOps (21,000-28,100 PLN), Security (20,600-26,900 PLN), Data/BI (21,000-26,900 PLN)

---

## Install

One command:

```bash
mkdir -p ~/.claude/skills/cost-estimate && curl -o ~/.claude/skills/cost-estimate/skill.md https://raw.githubusercontent.com/exhuman777/cost-estimate-skill/main/SKILL.md
```

Or clone and copy:

```bash
git clone https://github.com/exhuman777/cost-estimate-skill.git
mkdir -p ~/.claude/skills/cost-estimate
cp cost-estimate-skill/SKILL.md ~/.claude/skills/cost-estimate/skill.md
```

### Requirements

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) CLI
- `gh` CLI (GitHub CLI) for scanning GitHub URLs. Install: `brew install gh` then `gh auth login`

Local directory scanning works without `gh`. GitHub URL scanning needs it for cloning and API enrichment.

---

## What It Scans

| Signal | Method |
|--------|--------|
| Lines of code | `find` + `wc -l` across 17 extensions, excluding build artifacts |
| File types | Extension-based breakdown with counts |
| Dependencies | `package.json`, `requirements.txt`, `Cargo.toml`, `go.mod` |
| API integrations | Grep for fetch, axios, supabase, stripe, openai, anthropic, etc. |
| Smart contracts | Solidity file detection |
| Infrastructure | Vercel, Railway, Docker, GitHub Actions, Wrangler configs |
| Git history | Commit count, timespan, first/last commit dates |
| GitHub metadata | Stars, forks, contributors, languages, repo age, license (GitHub URLs only) |

---

## Example Output

Full sample report: [examples/example-output.md](examples/example-output.md)

```
PROJECT COST ESTIMATE -- acme-dashboard
Scanned: 2026-03-16 | 127 files | 14,280 LOC | TypeScript, CSS, Python
Source: github.com/acme/dashboard | Stars: 342 | Forks: 28 | Contributors: 5

--- COST BREAKDOWN ---

| Scenario              | Calendar Time | Human Hours | Total Cost (USD) |
|-----------------------|---------------|-------------|------------------|
| Solo Dev (US)         | ~7.6 mo       | 1,000       | $125,000         |
| Lean Startup (US)     | ~5.1 mo       | 1,000       | $110,000         |
| Growth Company (US)   | ~3.0 mo       | 1,000       | $125,000         |
| Enterprise (US)       | ~2.5 mo       | 1,000       | $169,000         |
| Polish Software House | ~3.0 mo       | 1,000       | $55,000          |
| Polish Internal Team  | ~3.0 mo       | 1,000       | $42,000 (168K PLN)|

--- THE HEADLINE ---

Claude worked for approximately 38 hours across 14 calendar days
and produced the equivalent of $125,000 in professional engineering value
-- roughly $3,289 per Claude hour.
```

---

## Edge Cases

- **No code files** -- stops and tells you
- **Monorepo** -- scans each project and sums
- **No git history** -- skips Claude hours section, asks you for active hours
- **Very small projects (<500 LOC)** -- flags high estimate variance
- **`gh` not installed** -- falls back to local-only scanning, warns you
- **Private repo without access** -- informs and stops
- **Very large repos (>100K files)** -- warns about scan time, considers sampling

---

## What This Doesn't Cover

- Marketing, legal, hosting costs, ongoing maintenance
- Design time beyond basic UI implementation
- Product management and stakeholder alignment
- Opportunity cost and time-to-market value
- Technical debt accumulation and future refactoring needs

The estimate covers **building the code that exists.** Not everything that goes into shipping a product.

---

## License

MIT

---

<p align="center">
  <em>Built by <a href="https://github.com/exhuman777">Exhuman</a> with Claude Code.</em>
</p>
