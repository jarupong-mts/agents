---
type: self
description: "Illustrative summary of bounded recovery in the harness specification"
source_refs:
  - kind: local
    target: "../../../harness.yaml"
  - kind: local
    target: "../../../prompts/implementer.md"
updated: "2026-10-14"
status: draft
example: true
---

# Retry Backoff Example

This is illustrative only. It summarizes the cited harness policy, not a measured
project failure or a new operational decision.

## Finding

An ordinary implementation or verification failure retries the affected Builder
slice within the configured budget. Preserve the failure evidence and use
root-cause before retrying; an ordinary failed check does not restart Intake.

## Consequences and limits

Consult the actual configured budget and failure artifact before recovery. This
example does not prescribe a retry delay or assert that any retry succeeded.
