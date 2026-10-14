---
name: harness-artifacts
description: Produce and validate structured Ticket, Plan, Task Result, Verification Result, and Review Result artifacts.
---

# Harness Artifacts

Use the artifact contract as an interface between roles.

- Return the required artifact type for the current stage, not a mixed narrative.
- Preserve stable identifiers, slice scope, dependencies, acceptance criteria,
  status, and recovery metadata when applicable.
- Tie material claims to exact evidence: command, file, diagnostic, source, or
  host result.
- Use the canonical status vocabulary (`verified`, `unknown`, `blocked`) for
  discovery and native verification.
- Never turn unknown or blocked evidence into approval or a success claim.
- Keep user-facing summaries concise, but do not omit unresolved concerns.

[schemas/artifacts.md](../../schemas/artifacts.md#knowledge-outcome) is authoritative
for Knowledge Outcome as well. Preserve `applicable`, `status`, nonempty `reason`,
`evidence`, completed `files_changed`, actual `checks`, and `remaining_work`.
Use `updated`, `no_change`, `blocked`, or `outside_scope` only under their contract
conditions. Required checks unavailable after final writes mean `blocked`; an
empty knowledge_updates list never proves assessment. An adapter must translate
this contract into its approved native mechanism rather than leave dangling links.
