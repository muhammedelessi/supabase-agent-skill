---
name: supabase-agent-skill
description: "Use when doing any task involving Supabase across web, mobile, backend, SaaS, APIs, or other applications. Covers Supabase Database, Auth, Edge Functions, Realtime, Storage, Vectors, Cron, Queues, client libraries and SSR integrations, Supabase CLI or MCP, schema changes, migrations, RLS and security audits, Postgres extensions, debugging, troubleshooting, logs, query optimization, indexes, connection management, locking, schema design, and Postgres best practices."
---

# Supabase Agent Skill

This is a platform-agnostic Supabase skill derived from and synchronized with the official Supabase `agent-skills` repository. It combines the official `supabase` skill with the official `supabase-postgres-best-practices` guidance so one skill can cover both Supabase product workflows and database engineering best practices.

## Core Supabase Guidance

For all Supabase tasks, follow the current official Supabase skill in:

- [references/official-supabase.md](references/official-supabase.md)

Treat that file as the authoritative operational guidance for Database, Auth, Edge Functions, Realtime, Storage, Vectors, Cron, Queues, client libraries, SSR integrations, CLI/MCP, migrations, debugging, logs, and Supabase-specific security behavior.

## Postgres Best Practices

Before writing or changing anything that lives in Postgres, also load:

- [references/postgres-best-practices/OVERVIEW.md](references/postgres-best-practices/OVERVIEW.md)

Then read the specific rule files in `references/postgres-best-practices/` that match the task.

The official rule categories are:

1. Query Performance — CRITICAL — `query-*`
2. Connection Management — CRITICAL — `conn-*`
3. Security & RLS — CRITICAL — `security-*`
4. Schema Design — HIGH — `schema-*`
5. Concurrency & Locking — MEDIUM-HIGH — `lock-*`
6. Data Access Patterns — MEDIUM — `data-*`
7. Monitoring & Diagnostics — LOW-MEDIUM — `monitor-*`
8. Advanced Features — LOW — `advanced-*`

Examples:
- Missing/partial/composite/covering indexes → read relevant `query-*` rules.
- RLS or privilege changes → read `security-*` rules.
- New tables, columns, constraints, keys, or partitions → read `schema-*` rules.
- Pooling, limits, prepared statements, or idle connections → read `conn-*` rules.
- Deadlocks or transaction contention → read `lock-*` rules.
- N+1, batching, pagination, or upserts → read `data-*` rules.
- EXPLAIN, pg_stat_statements, VACUUM/ANALYZE → read `monitor-*` rules.
- Full-text search or JSONB indexing → read `advanced-*` rules.

## Mandatory Safety Rules

- Verify current Supabase documentation and changelog before implementing behavior that may have changed.
- Never expose `service_role` or other secret keys in public clients.
- Enable and correctly design RLS for exposed data rather than treating authentication as authorization.
- Do not use `SECURITY DEFINER` as a shortcut for permission problems.
- Use both `USING` and `WITH CHECK` for UPDATE policies where ownership must remain enforced.
- Treat user-editable metadata as untrusted for authorization decisions.
- Prefer migration-safe, reversible database changes and verify the result after implementation.
- Run relevant database advisors or equivalent checks after schema/security changes when available.
- Do not repeatedly retry a failing approach; inspect docs, errors, and logs and change strategy.

## Verification

A task is not complete until the implemented behavior is verified. For database changes, verify schema state, migrations, permissions/RLS behavior, and representative queries. For Supabase product changes, verify the relevant Auth, Storage, Edge Function, Realtime, or API behavior.

## Skill Maintenance

This repository automatically synchronizes the official Supabase skill and Postgres best-practice references from `supabase/agent-skills` via GitHub Actions. Do not remove attribution or the upstream MIT license.

## Feedback

When the user reports incorrect or missing guidance from this skill, read:

- [references/skill-feedback.md](references/skill-feedback.md)
