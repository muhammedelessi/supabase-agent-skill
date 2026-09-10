# Supabase Agent Skill

Production-oriented Supabase guidance for AI coding agents across web, mobile, backend, SaaS, APIs, and other application types.

> **Version:** 1.0.0  
> **Status:** Public / reusable  
> **License:** MIT

This repository provides one stable `SKILL.md` entrypoint that combines and routes to the official Supabase agent guidance plus Supabase Postgres best practices. It is intentionally platform-agnostic and can be used in Lovable or other compatible agent workflows.

## What it covers

- Supabase Database, Auth, Edge Functions, Realtime, Storage, Vectors, Cron, and Queues
- Client libraries, SSR integrations, CLI/MCP, debugging, and logs
- Schema changes and migration safety
- Row Level Security (RLS), grants, authorization, and secrets handling
- Query performance, indexes, connections, locking, and data-access patterns
- Monitoring, diagnostics, schema design, and advanced Postgres features

## Import into Lovable

1. Open your Lovable workspace.
2. Go to **Settings -> Skills -> Import -> GitHub**.
3. Paste this repository URL:

```text
https://github.com/muhammedelessi/supabase-agent-skill
```

4. Import the skill and keep it enabled for projects that use Supabase.

The agent should invoke it automatically when a task involves Supabase, Postgres, Auth, RLS, SQL, migrations, indexes, Storage, Edge Functions, or related platform behavior.

## Example requests

```text
Review these Supabase RLS policies for authorization problems.
```

```text
Design a safe migration for this schema change and verify rollback risk.
```

```text
Investigate why this Supabase query is slow and recommend the right indexes.
```

```text
Review our Supabase Auth implementation before production release.
```

## Safety model

The skill treats authentication and authorization as separate concerns, does not allow secret/service-role keys in public clients, requires deliberate RLS design for exposed data, and favors migration-safe database changes with verification after implementation.

For database-specific work, it loads only the relevant Postgres best-practice references instead of injecting the entire rule set into every task.

## Repository structure

```text
.
├── SKILL.md
├── agents/
│   └── openai.yaml
├── references/
│   ├── official-supabase.md
│   ├── official-supabase-changelog.md
│   └── postgres-best-practices/
├── assets/
├── .github/workflows/
│   └── sync-supabase-skills.yml
├── CHANGELOG.md
├── CONTRIBUTING.md
└── LICENSE
```

## Upstream synchronization

The repository includes a GitHub Actions workflow that checks the official `supabase/agent-skills` repository and synchronizes the referenced Supabase guidance. The local `SKILL.md` remains the stable routing layer.

Upstream project:

```text
https://github.com/supabase/agent-skills
```

This repository is an **unofficial aggregation/repackaging** for convenient agent use. Supabase remains the source of the underlying official guidance.

## Contributing

Issues and pull requests are welcome. See `CONTRIBUTING.md` before proposing behavior changes.
