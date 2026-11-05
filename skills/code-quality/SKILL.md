---
name: code-quality
description: Shape and review code for simple complete solutions, suitable reuse, and readable structure. Use for implementation, review, and decisions about dependencies, abstractions, state boundaries, or test helpers and setup.
---

# Code Quality

Use these principles to make the smallest reliable change and avoid spending
effort or context on work that does not satisfy the approved goal.

1. **Think before acting.** Surface assumptions and tradeoffs. Ask when different
   interpretations would materially change the result.
2. **Choose the simplest sufficient solution.** Avoid speculative features,
   abstractions, configuration, and defensive code without a demonstrated need.
3. **Keep edits surgical.** Change only what the request and acceptance criteria
   require. Preserve nearby behavior and conventions; do not make unrelated
   cleanup changes.
4. **Define and verify the outcome.** Use observable acceptance criteria and the
   narrowest useful checks. Report what could not be verified.

When shaping code within the approved scope:

- Inspect suitable project helpers and conventions, then standard-library or
  platform features and installed dependencies. Choose by required behavior,
  compatibility, security, and maintenance cost, rather than the first match.
  Add a dependency when its benefits justify its cost.
- Keep data flow and state changes easy to trace. Limit mutable state to the
  scope that needs it, and derive values rather than synchronizing copies when
  that preserves the required behavior.
- Use abstractions to hide meaningful complexity or meet demonstrated
  requirements. Judge the work they save readers against the indirection they
  add; one caller alone is no reason to inline or remove a boundary.
- Give names domain meaning. Use comments for hidden rationale, invariants,
  and external constraints that the code cannot express clearly.
- Keep test setup, actions, assertions, and helpers readable. Let the test
  method determine behavior and coverage; concise tests must still expose
  what they exercise and why they fail.

For trivial, unambiguous work, apply the principles proportionately. Simplicity
does not justify omitting required behavior, tests, or safety controls.
This method applies within the approved scope and does not replace test-driven
development, root-cause investigation, independent review, security work, or
required checks.

Source influences: [Ponytail](https://github.com/DietrichGebert/ponytail/blob/96608e078b2d5ea607c5c3b8b5a54d1c1fba6846/skills/ponytail/SKILL.md)
and [Minimize Reader Load](https://github.com/cursor/plugins/blob/bb68f2365eceafa0cb2d253112f675acf5f144cc/pstack/skills/principle-minimize-reader-load/SKILL.md).
Full MIT notices are retained in [LICENSE](LICENSE).
