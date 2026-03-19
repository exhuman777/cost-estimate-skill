# Example Output: cost-estimate skill (small project)

This is a real report from scanning [exhuman777/breathe](https://github.com/exhuman777/breathe) -- a terminal meditation app with 3D wireframe rendering, sacred geometry, and breathing exercises. Shows the skill works on small projects too.

```
PROJECT COST ESTIMATE -- breAIth
Scanned: 2026-03-19 | 6 files | 1,719 LOC | Python, HTML, Shell
Source: github.com/exhuman777/breathe | Stars: 1 | Forks: 0 | Contributors: 1
Created: 2026-03-05 | Last push: 2026-03-07 | Age: 2 days active dev

--- CODEBASE ANALYSIS ---

GitHub Stats:     1 star, 0 forks, 1 contributor (exhuman777)
GitHub Languages: Python 99.7%, Shell 0.3%
Repository Size:  74 KB | License: none

Languages (local scan):
  Python:  892 LOC  (1 file)  -- full curses TUI: 3D rendering, breathing engine, state machine
  HTML:    821 LOC  (1 file)  -- landing page (docs/index.html)
  Shell:     6 LOC  (2 files) -- Claude Code session hooks
  MD:      211 LOC  (2 files) -- README, CLAUDE.md

Dependencies:     0 external packages (pure Python stdlib: curses, math, os, json, argparse)
API Integrations: None (standalone terminal app, Claude Code hooks via file-based IPC)
Infrastructure:   None (local tool, no deployment infra)
Complexity Score: 2.6/5

  Frontend complexity:   4/5  -- curses TUI, 3D wireframe/sacred geometry/Lissajous rendering, starfield, animations
  Backend complexity:    2/5  -- single-file state machine (SETUP/IDLE/ACTIVE/JOURNAL), file-based detection
  Integrations:          2/5  -- Claude Code hooks, /tmp file-based IPC, JSONL mtime monitoring
  Infrastructure:        1/5  -- local-only, no deploy
  Domain expertise:      4/5  -- breathing techniques (box/4-7-8/focus/Wim Hof), 3D rotation matrices, Lissajous math
  Real-time features:    4/5  -- 60fps animation loop, real-time state transitions, file mtime polling
  Security:              1/5  -- local-only, no auth, no network

--- ESTIMATED HUMAN EFFORT ---

Base hours:    86 (at 20 LOC/hr -- specialized terminal UI with 3D math)
Complexity:    86 * 0.86 = 74 hours
With overhead: 74 * 1.75 = 130 hours (planning, review, QA, iteration)

--- COST BREAKDOWN ---

| Scenario              | Calendar Time | Human Hours | Total Cost (USD)  |
|-----------------------|---------------|-------------|-------------------|
| Solo Dev (US)         | ~1 month      | 130         | $16,300           |
| Lean Startup (US)     | ~3 weeks      | 130         | $14,300           |
| Growth Company (US)   | ~2 weeks      | 130         | $19,500           |
| Enterprise (US)       | ~1 week       | 130         | $22,000           |
| Polish Software House | ~3 weeks      | 130         | $7,200            |
| Polish Internal Team  | ~1 month      | 130         | $4,300 (17K PLN)  |

--- POLISH MARKET CONTEXT (2026) ---

If built by a Polish software house for a US/EU client:
- Blended rate: ~$55/hr (vs US $125/hr -- 2.3x cheaper)
- Same quality tier as Western Europe, EU timezone overlap
- Monthly team burn: ~17,000 PLN/mo for 1 mid dev
- Poland: 400,000+ developers, 1,050+ software houses (Clutch)
- #1 IT outsourcing destination in CEE

What Polish devs actually earn (B2B net/month):
- Senior: 25,000 PLN (~$6,250)    | US equivalent: $17,500/mo
- Mid:    17,000 PLN (~$4,250)    | US equivalent: $11,900/mo
- Junior: 10,000 PLN (~$2,500)    | US equivalent: $7,900/mo
- US costs 2.8-3.2x more for equivalent seniority

Polish reality check:
- A Polish mid dev (B2B) could build this in ~1 month for 17K PLN ($4,300)
- Same work in US: $16,300 -- Poland saves ~74%
- A Polish software house would quote ~$8,000-10,000
  (minimum project fees apply for small scopes)
- For a project this size, freelancer is more practical than a team

--- VALUE PER CLAUDE HOUR ---

10 commits over 2 calendar days (Mar 5-7, 2026).
Estimated ~5 Claude hours of active interaction.

| Metric                    | Value                    |
|---------------------------|-----------------------------|
| Engineering value (solo)  | $16,300                  |
| Full team value (growth)  | $19,500                  |
| Claude active hours       | ~5                       |
| $/Claude hour             | $3,260/hr                |
| Speed multiplier          | 26x faster               |
| Claude cost (Pro sub)     | ~$2                      |
| Net savings vs Solo (US)  | $16,298                  |
| Net savings vs Polish SH  | $7,198                   |
| ROI                       | 8,150x                   |

--- THE HEADLINE ---

Claude worked for approximately 5 hours across 2 calendar days
and produced the equivalent of $16,300 in professional engineering value
-- roughly $3,260 per Claude hour.

A US growth-stage company would spend $19,500 and 2 weeks.
A Polish software house would quote ~$9,000 and 3 weeks.
A Polish internal team would burn 17,000 PLN over 1 month.

For 892 lines of Python: a full terminal meditation app with 3D wireframe
rendering, sacred geometry, Lissajous curves, 4 breathing techniques,
Claude Code session detection via file-based IPC, and a journal system.
Zero dependencies. Pure stdlib.

---
Assumptions:
1. Rates based on US + Polish market averages (2025-2026)
   Sources: Salary.com, Glassdoor, Bulldogjob, NoFluffJobs, JustJoinIT
2. Mid-level Python developer as baseline (specialized terminal UI work)
3. 20 LOC/hr reflects the 3D math, curses rendering, and animation complexity
4. Does not include: marketing, hosting, ongoing maintenance
5. Polish rates: B2B net (developer take-home). Software house rates include 30-40% margin.
6. 1 USD ~ 4.0 PLN (March 2026)
7. Claude hours estimated from 10 commits over 2-day active span
8. Small project (<2K LOC) -- estimate has higher variance than larger codebases
```
