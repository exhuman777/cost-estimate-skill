# cost-estimate

A Claude Code skill that scans any codebase and estimates what it would cost a real development team to build it.

Point it at a GitHub repo URL or local directory. It analyzes complexity, calculates hours, and cross-references 2025-2026 market rates for US and Polish developers. Shows the ROI of AI-assisted development vs. traditional teams.

## What you get

- **Codebase analysis**: LOC breakdown by language, dependencies, API integrations, infrastructure detection
- **Human effort estimate**: Hours calculated from LOC + complexity scoring with 1.75x overhead multiplier
- **Cost breakdown across 6 scenarios**: Solo Dev, Lean Startup, Growth Company, Enterprise (all US), Polish Software House, Polish Internal Team
- **Polish market context**: Real B2B/UoP salary data from Bulldogjob, JustJoinIT, NoFluffJobs (2025-2026)
- **AI comparison**: Value per Claude hour, speed multiplier, ROI vs. every scenario
- **GitHub enrichment**: When scanning a GitHub URL, pulls stars, forks, contributors, language breakdown, and repo age from the API

## Install

Copy `SKILL.md` into your Claude Code skills directory:

```bash
# Clone this repo
git clone https://github.com/exhuman777/cost-estimate-skill.git

# Copy the skill file
mkdir -p ~/.claude/skills/cost-estimate
cp cost-estimate-skill/SKILL.md ~/.claude/skills/cost-estimate/skill.md
```

Or just download the file directly:

```bash
mkdir -p ~/.claude/skills/cost-estimate
curl -o ~/.claude/skills/cost-estimate/skill.md https://raw.githubusercontent.com/exhuman777/cost-estimate-skill/main/SKILL.md
```

## Usage

```
# Scan a GitHub repo (clones it, scans, cleans up)
/cost-estimate github.com/vercel/next.js

# Full HTTPS URL works too
/cost-estimate https://github.com/shadcn-ui/ui

# Scan a local directory
/cost-estimate ~/projects/my-app

# Scan current directory
/cost-estimate
```

## Requirements

- [Claude Code](https://claude.ai/code) CLI
- `gh` CLI (GitHub CLI) -- for GitHub URL scanning and API enrichment. Install: `brew install gh`
- `gh auth login` -- must be authenticated for API calls

Local directory scanning works without `gh`.

## What it scans

| What | How |
|------|-----|
| Lines of code | `find` + `wc -l` across 17 file extensions, excluding build artifacts |
| File types | Extension-based breakdown |
| Dependencies | `package.json`, `requirements.txt`, `Cargo.toml`, `go.mod` |
| API integrations | Grep for fetch, axios, supabase, stripe, openai, etc. |
| Smart contracts | Solidity file detection |
| Infrastructure | Vercel, Railway, Docker, GitHub Actions, Wrangler configs |
| Git history | Commit count, timespan, active development days |
| GitHub metadata | Stars, forks, contributors, languages, repo age (GitHub URLs only) |

## Rate data sources

- **US rates**: Salary.com, Glassdoor, industry surveys (2025-2026)
- **Polish rates**: Bulldogjob IT Community Report 2025 (4,800 respondents), JustJoinIT 2026 (111K+ postings), NoFluffJobs
- **Exchange rate**: 1 USD ~ 4.0 PLN (March 2026)

The Polish market data is a unique differentiator. No other estimation tool provides this level of detail on Eastern European dev economics, including B2B vs. UoP contract comparisons, software house margins, and specialization-specific salary bands.

## Example output

See [examples/example-output.md](examples/example-output.md) for a full sample report.

## License

MIT
