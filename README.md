# /market-research

Claude Code skill for rough market research in Russia.

Collects data from open sources via web search, optionally pulls search demand from Yandex Wordstat, and outputs a structured report in Russian.

## What it does

Takes a topic and produces a compact market overview:

- **Market size** — volume, growth, CAGR, forecasts with sources
- **Key players** — companies, positioning, market shares
- **Audience** — segments, size, willingness to pay
- **Search demand** — Yandex Wordstat data (if available)
- **Trends** — what's growing, what's declining, tech shifts
- **Barriers to entry** — regulation, capital, network effects
- **Opportunities** — underserved niches, entry ideas

## Usage

```
/market-research онлайн-курсы по программированию
/market-research доставка готовой еды в Москве
/market-research найм фиолетовых воротничков
```

## How it works

1. Parses the topic from user input
2. Runs 4-6 parallel web searches (WebSearch / Exa) for market data, players, trends, audience
3. Optionally calls `/yandex-wordstat` for B2C topics to get real search volume
4. Synthesizes everything into a structured report with numbered sources

## Install

Copy `SKILL.md` to your Claude Code skills directory:

```bash
mkdir -p .claude/skills/market-research
cp SKILL.md .claude/skills/market-research/
```

Or install via slash command in Claude Code:

```
/install-skill https://github.com/2vlad/market-research-skill
```

## Principles

- All output in Russian
- Every number has a source link
- "No data" is better than fiction
- Fresh data preferred (2024-2026)
- Compact — facts, numbers, conclusions, no fluff
