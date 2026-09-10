# Supabase Agent Skill

Production-oriented Supabase guidance for AI coding agents across web, mobile, backend, SaaS, APIs, and other application types.

> **Version:** 1.0.0  
> **Status:** Public / reusable  
> **License:** MIT

This repository provides one stable `SKILL.md` entrypoint that combines and routes to the official Supabase agent guidance plus Supabase Postgres best practices. It is intentionally **platform-agnostic** and is designed to work across Agent Skills-compatible coding environments.

## Compatible environments

This skill can be used with:

- Lovable
- OpenAI Codex
- Cursor
- Visual Studio Code with GitHub Copilot Agent Skills
- Google Antigravity
- Other coding agents and vibe-coding tools that support the Agent Skills / `SKILL.md` format

The skill logic is not tied to any editor. Only the installation method changes between platforms.

## What it covers

- Supabase Database, Auth, Edge Functions, Realtime, Storage, Vectors, Cron, and Queues
- Client libraries, SSR integrations, CLI/MCP, debugging, and logs
- Schema changes and migration safety
- Row Level Security (RLS), grants, authorization, and secrets handling
- Query performance, indexes, connections, locking, and data-access patterns
- Monitoring, diagnostics, schema design, and advanced Postgres features

## Installation and usage

### Lovable

Open your Lovable workspace and go to:

**Settings -> Skills -> Import -> GitHub**

Paste:

```text
https://github.com/muhammedelessi/supabase-agent-skill
```

Keep the skill enabled for projects that use Supabase.

### OpenAI Codex

Use Codex's skill installer to install the skill from this GitHub repository, or place the repository as a skill directory under your project's Agent Skills location, for example:

```text
.agents/skills/supabase-agent-skill/
```

The directory must contain this repository's `SKILL.md` and supporting files.

### Cursor

Clone or copy this repository into one of Cursor's supported skill locations.

Project-level examples:

```text
.agents/skills/supabase-agent-skill/
.cursor/skills/supabase-agent-skill/
```

User-level examples:

```text
~/.agents/skills/supabase-agent-skill/
~/.cursor/skills/supabase-agent-skill/
```

Cursor can discover the skill automatically when the request matches its description, and it can also be invoked from Agent chat.

### Visual Studio Code / GitHub Copilot

Copy or clone the repository into a supported Agent Skills directory.

Project-level examples:

```text
.github/skills/supabase-agent-skill/
.agents/skills/supabase-agent-skill/
```

User-level examples:

```text
~/.copilot/skills/supabase-agent-skill/
~/.agents/skills/supabase-agent-skill/
```

VS Code can load the skill automatically when relevant or invoke it directly from Copilot Chat.

### Google Antigravity

Project/workspace scope:

```text
<project-root>/.agents/skills/supabase-agent-skill/
```

Global scope for Antigravity IDE:

```text
~/.gemini/config/skills/supabase-agent-skill/
```

Use the project location when the skill should travel with the repository, or global scope when you want it available across projects on your machine.

### Other Agent Skills-compatible tools

Place this repository in the tool's supported skills directory so that `SKILL.md` is the entrypoint. If the tool supports the open Agent Skills format, the core workflow should remain portable even when its discovery or installation UI differs.

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
