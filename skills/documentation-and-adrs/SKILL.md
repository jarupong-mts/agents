---
name: documentation-and-adrs
description: Maintain project documentation and distinct durable knowledge with clear authority, evidence, and ADR history.
---

# Documentation and ADRs

This is the local materialization default. Preserve its historical influence from
knowledge-base; source selection and provenance remain separate.

Follow the [record-boundary policy](../../SPEC.md#documentation-knowledge-and-run-artifacts).
Project documentation is the authoritative home for concepts, PRDs, requirements,
specifications, design, architecture, and guides. Edit it only within the applicable
approved scope and ownership; knowledge curation grants no general permission to
write it or silently establish or revise requirements. Keep execution-specific
Tickets, Plans, results, checks, and progress in their approved run-artifact home.

For knowledge work, follow [knowledge-base](../knowledge-base/SKILL.md) and the
target's approved categories and protection policy. Read relevant existing records
first; update or merge before creating another page. Retain distinct, reusable,
evidence-backed discoveries, constraints, qualifications, procedures, and recurring
failure causes. Keep one authoritative home per substantive record: cite canonical
documents and decisions through `source_refs` instead of copying their contents.
Related topics may overlap when the learning and its evidence are distinct.
Preserve suitable approved homes and ownership; classify by purpose and approved
configuration, not folder name. Reuse requires compatible discovered or approved
purpose and ownership; a general project-documentation area is not an implicit
learning or run-artifact home. Never invent unresolved destinations. Exclude
transcripts, routine diaries, copied code, and unsupported claims.

Write configured knowledge pages with complete YAML metadata and typed
`source_refs`; ordinary project documents do not inherit this frontmatter from
their topic or location. Keep indexes navigational, preserve raw sources, and
change locked external compilations only during an explicit source re-sync.
Record versions, limitations, and unresolved contradictions rather than
overwriting the conflicting evidence.

## Architecture decision records

Use an ADR for a consequential decision whose alternatives, rationale, or history
will matter later. Preserve the target's approved decision-record home and
ownership. The reusable [ADR template](../../knowledge/_template/adr.md) provides
`Context`, `Decision`,
`Reasons`, `Rejected alternatives`, `Consequences`, `Open questions`, `History`,
and `Supersession`. Keep those sections and earlier history when changing status.

ADR frontmatter uses `type: adr` and the ordinary required metadata. Its statuses
are `Proposed`, `Accepted`, `Superseded`, and `Deprecated`:

- `Proposed` records a proposal without asserting human acceptance.
- `Accepted` requires `human_decision` with nonempty `actor`, actual ISO date
  `decided_at`, and an existing typed local/artifact `evidence_ref`. Read the
  retained human decision evidence; agent inference or a command alone cannot
  establish acceptance.
- `Superseded` requires typed local/artifact `superseded_by` pointing to an
  existing replacement, plus preserved `History` describing the transition.
- `Deprecated` requires nonempty `deprecation_reason` and preserved `History`.

Do not fabricate acceptance, timestamps, source references, or check outcomes.
When no human decision evidence exists, keep a proposal rather than writing an
Accepted record. The [illustrative ADR](../../knowledge/_example/self/adr-0001-knowledge-layout.md)
shows a Proposed record and does not assert a project decision.

Maintain affected metadata, references, indexes, navigation hints, and action
logs. Run the configured knowledge checks after the final write, including logs,
then return the Knowledge Outcome with actual results. Failed or unavailable
required checks are `blocked`; a reasoned assessment with no eligible learning
is `no_change`.

When materializing this method, the adapter must include or translate the required
ADR template and knowledge contract into approved native destinations and rewrite
references. Applicable final-write integrity checks remain mandatory; map them to
a compatible existing target checker, translated checks, or the optional reference
checker. Only selecting that checker requires its Python 3.10+ standard-library
runtime and target-specific layout/check command. Its maintainer tests are not
automatically created, run, or copied by workflow adoption. Inventory included,
translated, referenced, and omitted assets with reasons. The illustrative ADR,
log, and layout are reference examples, not required downstream files. Rewrite or
remove projected links; never install this repository's whole example knowledge tree.
