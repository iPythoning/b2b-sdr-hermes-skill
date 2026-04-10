# B2B SDR Agent Skill for Hermes

> Autonomous AI Sales Development Representative — finds buyers, qualifies leads, sends personalized outreach, and manages your entire B2B export pipeline 24/7 via WhatsApp, Email, and Telegram.

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Hermes Agent](https://img.shields.io/badge/Hermes-Agent%20Skill-blue)](https://github.com/NousResearch/hermes-agent)

## What It Does

| Stage | Action | Channel |
|-------|--------|---------|
| Lead Discovery | Web search for potential buyers in target markets | Automated |
| Lead Capture | Auto-create CRM records from inbound messages | WhatsApp / Email / Telegram |
| BANT Qualification | Score leads through natural conversation | WhatsApp / Telegram |
| Research & Enrichment | Company background, decision-maker identification | Web search |
| Quotation | Generate quotes with shipping + payment terms | Email / WhatsApp |
| Outreach Sequences | 4-touch personalized cold email campaigns | Email |
| Pipeline Management | Daily/weekly reports, stalled lead alerts | Cron |
| Nurture | Automated re-engagement for cold/won/lost leads | Multi-channel |

## Install

```bash
# One command — installs the skill into your Hermes agent
hermes skills install github:iPythoning/b2b-sdr-hermes-skill
```

For **Claude Code / Codex / Cursor** users (via [skills.sh](https://skills.sh)):
```bash
npx skills add iPythoning/b2b-sdr-hermes-skill
```

Or manually:
```bash
cd ~/.hermes/skills
git clone https://github.com/iPythoning/b2b-sdr-hermes-skill.git b2b-sdr-agent
```

## Setup

After installation, start a new Hermes session and say:

> "Set up the B2B SDR agent for my business"

The skill will guide you through:
1. Company name, industry, and target markets
2. CRM setup (Google Sheets, Notion, JSON file, or HubSpot)
3. Cron schedule activation for pipeline inspections
4. WhatsApp pairing (if not already connected)

## Cron Schedules

The skill includes 7 pre-configured inspection routines:

| Schedule | Frequency | What It Does |
|----------|-----------|-------------|
| New leads | Every 4 hours | Check for unprocessed inbound leads |
| Stalled leads | Weekdays 9:00 | Flag leads with no contact in 5+ days |
| Quote follow-up | Weekdays 10:00 | Draft follow-ups for sent quotes |
| Email sequences | Daily 11:00 | Execute Day 3/7/14 outreach follow-ups |
| Lead discovery | Daily 10:00 | Search for new prospects in target markets |
| Weekly report | Monday 9:00 | Full pipeline analytics |
| Nurture check | Monday 9:00 | Re-engagement for cold/won/lost contacts |

## Requirements

- [Hermes Agent](https://github.com/NousResearch/hermes-agent) v0.7.0+
- WhatsApp connected via `hermes whatsapp` (for WhatsApp channel)
- Web search enabled (DuckDuckGo built-in, or Brave/Jina API key for better results)
- Email: configure via `hermes agentmail` or SMTP settings for outreach sequences

## CRM Options

| Type | Best For | Setup |
|------|----------|-------|
| Google Sheets | Quick start, team visibility | Skill auto-creates the sheet |
| JSON file | Self-hosted, no external deps | `~/sdr-crm.json` |
| Notion | Rich formatting, databases | Provide Notion API key |
| HubSpot | Enterprise, existing CRM | Provide HubSpot API key |

## From OpenClaw?

If you were using the [b2b-sdr-agent-template](https://github.com/iPythoning/b2b-sdr-agent-template) on OpenClaw, migrate with:

```bash
hermes claw migrate --preset full
hermes skills install github:iPythoning/b2b-sdr-hermes-skill
```

Your SOUL.md, MEMORY.md, and CRM data carry over automatically.

## Managed Version

Want AI SDR as a managed service with built-in CRM, WhatsApp relay, and team dashboard? Try [PulseAgent](https://pulseagent.io) — 7-day free trial, no credit card required.

## License

MIT — use it however you want.

## Contributing

Issues and PRs welcome. The skill is designed to be forked and customized for your industry. See `examples/` for industry-specific configurations.
