---
name: "tenable-quick-wins-dashboard"
author: "rafansmpj"
github_url: "https://github.com/rafansmpj/Tenable-One-Claude-MCP-SKILLS"
description: >
  Generates an interactive Executive Quick Wins Dashboard for reducing Tenable One
  Exposure Score in cumulative phases of 10%-20%-30%-40%-50%. Connects to the Tenable
  MCP, calculates which vulnerabilities and actions generate the greatest score reduction
  with minimum effort (high VPR × affected assets × fix ease), and presents an interactive
  visual dashboard with cumulative remediation phases, industry benchmark, and score
  projection. Ideal for C-Level, Board, CISO, and VP of IT audiences.
license: "MIT"
type: "skill"
tier: "community"
tags:
  - "tenable-one"
  - "exposure-management"
  - "vulnerability-management"
  - "executive-dashboard"
  - "quick-wins"
  - "remediation"
  - "risk-reduction"
  - "ciso"
  - "c-level"
  - "mcp"
  - "claude-code"
framework: "Claude Code SKILL"
integrations:
  - "Tenable One"
  - "Tenable Vulnerability Management"
date_added: 2026-06-22
---

# Tenable Quick Wins Executive Dashboard

An interactive Claude Code skill that generates a phased remediation roadmap for reducing your Tenable One Exposure Score, designed for C-Level, Board, and CISO audiences.

## What it does

- Connects to the **Tenable One MCP** to collect real exposure data (Exposure Score, vulnerabilities, Crown Jewels, attack path chokepoints, and industry benchmark)
- Calculates a **Quick Win Score** for each finding: `(VPR × affected_assets × breadth_factor) / effort + crown_jewel_bonus + chokepoint_bonus`
- Builds **5 cumulative remediation phases** (-10% → -20% → -30% → -40% → -50% Exposure Score reduction), each showing the incremental actions needed
- Delivers a **React-based interactive dashboard** with:
  - Executive header with current score, target, and benchmark
  - Visual gauge/speedometer with phase markers
  - Clickable phase cards with detailed action tables (Plugin ID, type, affected assets, VPR, score delta, Crown Jewel flag, suggested owner)
  - Cumulative score progression chart vs. industry peers
  - Benchmark vs. peers comparison card
  - Board-ready executive summary in plain business language

## Use cases

Invoke this skill whenever the user asks for:
- Quick wins, ganhos rápidos, roadmap de remediação
- "How do I reduce my Exposure Score?"
- "Which vulnerabilities should I close first?"
- "Plan to reduce my score by 50%"
- "Remediation prioritization for C-Level"
- "Por onde começar / maior impacto com menor esforço"
- Industry benchmark comparison

## Algorithm

The Quick Win Score prioritizes:
1. **VPR ≥ 9.0** (exploitability weight)
2. **Breadth** — vulnerabilities affecting many assets simultaneously
3. **Low effort** — single patch covering multiple assets
4. **Crown Jewel bonus** (+30% weight if finding affects a Crown Jewel)
5. **Chokepoint bonus** (+20% if the asset is an attack path chokepoint)

## Dashboard design

Uses the Tenable brand palette:
- Background: `#44494B` | Accent: `#E7FF00` | Blue: `#4EA5FF`
- Green: `#71FFC6` | Purple: `#BB8FF2` | Orange: `#FF8837`

Each phase uses a distinct color (F1=Green, F2=Blue, F3=Purple, F4=Orange, F5=Yellow).

## Customizations supported

| Request | Adaptation |
|---------|-----------|
| "Only phases 1 and 2" | Generate up to 20% reduction only |
| "Focus on Cloud / Identity / OT" | Filter Quick Wins by domain |
| "Version in English / PT-BR / ES" | Multilingual output |
| "For the board" | Expand executive summary, condense technical tables |
| "Add regulatory context" | Map actions to LGPD, ISO 27001, NIST CSF, PCI-DSS, BACEN |
| "Show only Crown Jewels" | Filter quick wins affecting Crown Jewels |
| "Export as project plan" | Generate table with owner, deadline, status, dependencies |
| "Group by owner" | Reorganize tables by responsible team |

## Requirements

- Claude Code with Tenable One MCP connected
- Tenable One license with Lumin/Exposure View enabled (for Exposure Score and benchmark data)
- If MCP is unavailable, the skill generates a DEMO dashboard with realistic mock data and a "DEMO — illustrative data" watermark

## Installation

Copy `SKILL.md` into your Claude Code skills directory:

```
/mnt/skills/user/tenable-quick-wins-dashboard/SKILL.md
```

Then invoke via any trigger phrase above (e.g., "quick wins", "reduce my exposure score", "roadmap de remediação").
