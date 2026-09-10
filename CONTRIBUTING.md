# Contributing

Thanks for helping improve this skill.

## Before opening a change

- Keep `SKILL.md` concise and focused on routing and safety-critical behavior.
- Prefer official Supabase guidance for platform-specific rules.
- Preserve attribution and upstream licensing for synchronized Supabase content.
- Avoid duplicating large upstream references in the entrypoint.
- Do not weaken RLS, Auth, secret-handling, migration-safety, or verification requirements without a documented reason.

## Pull requests

Describe the problem, the proposed change, why it improves agent behavior, and how the change was verified. If the change depends on current Supabase behavior, link the relevant official documentation or upstream change.

## Versioning

Use semantic versioning for deliberate local behavior changes. Upstream synchronized reference refreshes do not require a local major version unless they materially change the skill contract.
