# Supabase Agent Skill

A general-purpose Supabase skill for AI coding agents and development workflows across web, mobile, backend, SaaS, APIs, and other application types.

This repository combines the two official Supabase agent skills currently published in `supabase/agent-skills`:

- `skills/supabase`
- `skills/supabase-postgres-best-practices`

It retains the upstream MIT license and is intentionally platform-agnostic. It is not tied to Lovable, NHM, or any specific project.

## What it covers

The combined skill includes guidance for Supabase Database, Auth, Edge Functions, Realtime, Storage, Vectors, Cron, Queues, client libraries, SSR integrations, CLI/MCP, schema changes, migrations, RLS, security, debugging, logs, query performance, indexes, connection management, schema design, locking, data-access patterns, monitoring, and advanced Postgres features.

## Repository structure

- `SKILL.md` — unified entrypoint used by agents
- `references/official-supabase.md` — synchronized copy of the official Supabase skill
- `references/official-supabase-changelog.md` — synchronized upstream skill changelog
- `references/postgres-best-practices/OVERVIEW.md` — official Supabase Postgres best-practices skill
- `references/postgres-best-practices/*.md` — complete official Postgres best-practice rule set
- `references/postgres-best-practices/CHANGELOG.md` — synchronized upstream changelog
- `references/skill-feedback.md` — official feedback workflow
- `assets/feedback-issue-template.md` — official feedback template
- `agents/openai.yaml` — optional ChatGPT UI metadata
- `.github/workflows/sync-supabase-skills.yml` — weekly/manual synchronization from Supabase upstream
- `LICENSE` — upstream MIT license

## Automatic updates

A GitHub Actions workflow checks the official `supabase/agent-skills` repository weekly and can also be run manually. When Supabase changes either official skill or its Postgres reference rules, the synchronized files in this repository are updated automatically.

The unified `SKILL.md` remains the stable entrypoint and tells the agent when to load the official Supabase guidance and when to load the relevant Postgres rule files.

## Upstream

https://github.com/supabase/agent-skills

This repository is an unofficial repackaging for convenient use by AI agents. Supabase remains the source of the underlying official guidance.
