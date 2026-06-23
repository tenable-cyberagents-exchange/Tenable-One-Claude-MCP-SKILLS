# tenable-quick-wins-dashboard

> A Claude Code skill for Tenable One — generates an interactive Executive Quick Wins Dashboard for reducing your Exposure Score in 5 cumulative phases.

## Overview

This skill connects to the **Tenable One MCP** and produces a React-based interactive dashboard that prioritizes which vulnerabilities to close first, organized in cumulative remediation phases targeting -10% to -50% Exposure Score reduction. Designed for **C-Level, Board, CISO, and VP of IT** audiences.

## How it works

1. Collects live data via Tenable One MCP (Exposure Score, vulnerabilities, Crown Jewels, attack path chokepoints, industry benchmark)
2. Calculates a **Quick Win Score** per finding: `(VPR × breadth × affected_assets) / effort + crown_jewel_bonus + chokepoint_bonus`
3. Stacks findings into 5 cumulative phases aligned to score reduction milestones
4. Renders an interactive dashboard with gauge, phase cards, progression chart, and board-ready executive summary

## Installation

Copy `SKILL.md` to your Claude Code skills directory:

```bash
cp SKILL.md /mnt/skills/user/tenable-quick-wins-dashboard/SKILL.md
```

## Usage

In a Claude Code session with the Tenable One MCP connected, use any of these triggers:

```
quick wins
roadmap de remediação
reduce my Exposure Score
quais vulnerabilidades fechar primeiro
plano de 50% de redução
```

## Requirements

- Claude Code (Pro, Max, Team, or Enterprise)
- Tenable One MCP configured with valid API keys
- Tenable One license with Lumin/Exposure View enabled

## Dashboard features

- **Gauge / speedometer** with phase markers and industry benchmark line
- **5 clickable phase cards** (-10% → -50%), each expanding a detailed remediation table
- **Score progression chart** vs. industry peers
- **Benchmark card** showing current vs. target percentile
- **Executive summary** in plain business language (board-ready)

## Color palette

| Color | Hex | Usage |
|-------|-----|-------|
| Background | `#44494B` | Base |
| Accent | `#E7FF00` | Titles, highlights |
| Green | `#71FFC6` | Phase 1, positive indicators |
| Blue | `#4EA5FF` | Phase 2, charts |
| Purple | `#BB8FF2` | Phase 3 |
| Orange | `#FF8837` | Phase 4, alerts |
| Yellow | `#E7FF00` | Phase 5 |

## License

MIT © 2026 rafansmpj
