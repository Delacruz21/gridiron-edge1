# gridiron-edge1
Point-in-time fantasy football decision system for a private Yahoo league.

Quick start
# Install uv: https://docs.astral.sh/uv/
make install

# Copy and fill in credentials
cp .env.example .env

# Run migrations
make migrate

# Health check (requires Yahoo OAuth tokens)
ge yahoo health
CLI
ge --help
ge yahoo health
ge yahoo ingest-settings
ge snapshot daily
Docs
Build plan
Schema
Deferred features
Required credentials
Set in .env (never commit):

Variable	Purpose
DATABASE_URL	Postgres DSN
YAHOO_CLIENT_ID	Yahoo OAuth app
YAHOO_CLIENT_SECRET	Yahoo OAuth app
YAHOO_REDIRECT_URI	OAuth callback
FANTASYPROS_API_KEY	ECR/projections/ADP
YAHOO_LEAGUE_ID	Default: 354918
YAHOO_TEAM_ID	Your team ID
DISCORD_WEBHOOK_URL	Phase 2 output (optional)
