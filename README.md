# gridiron-edge

A personal, single-league fantasy football decision-support tool. Built and used by one person (me) for one private Yahoo Fantasy Football league I play in.

**Fantasy data provided by [Yahoo Fantasy](https://football.fantasysports.yahoo.com/).**

## What it does

Every day it takes a point-in-time snapshot of my league's state and of public NFL data, then computes roster-specific recommendations for my own team:

- Waiver claim and free-agent rankings, adjusted for my league's scoring, roster size, and what's actually available
- Start/sit and streaming suggestions
- A manual draft board for our offline draft
- An audit trail of every recommendation so I can evaluate my own decisions later

It's a research project. The point is learning which signals produce better decisions than consensus, not producing generic rankings.

## Data sources

| Source | Data | Access |
|---|---|---|
| Yahoo Fantasy Sports API | League settings & scoring, rosters, transactions/waivers, available-player pool, matchups, standings, offline-draft results | Read-only, OAuth 2.0, my account only |
| nflverse | Play-by-play, weekly stats, snap counts, schedules, depth charts | Public |
| FantasyPros | Consensus rankings, projections, ADP, news | Licensed API |
| Vegas lines | Spreads, totals | Public/free tier |

## Scope and data handling

- One user, one league (14 teams, private).
- Read-only. The tool never writes to Yahoo.
- All data is stored locally on my own machine in Postgres. Nothing is published, shared, resold, or redistributed.
- Request volume is a once-daily snapshot plus a few refreshes on game days — a few hundred requests/day at most.

## Stack

Python 3.12, PostgreSQL, SQLAlchemy/Alembic, Streamlit for the draft board. Runs as a scheduled job on a home machine.

## Status

Phase 0 (data spine) in progress. See `docs/PLAN.md`.

## License

Personal use. Not for redistribution.
