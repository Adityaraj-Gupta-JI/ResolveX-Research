# Development workflow — ResolveX

Status: adopted operational policy, version 0.2.

## Core cycle: SPEC → IMPLEMENT → VERIFY → AUDIT → RECORD

1. **Intake:** Open a GitHub Issue with a stable ticket ID, acceptance criteria, risks, and links to relevant specifications.
2. **Investigate:** Read the affected code, tests, ADRs, prior ticket notes, and relevant formal models. Record assumptions before changing behavior.
3. **Design:** Define the smallest change, expected proof obligations, test cases, and a rollback plan. Update an ADR for consequential design decisions.
4. **Implement:** Work on a focused branch. Prefer small functions, descriptive types, reusable modules, and comments explaining *why*, not narrating obvious code. Do not embed secrets.
5. **Verify:** Format, lint, test, run representative examples, check formal properties where relevant, and inspect changes. Record actual results; do not claim checks were run when they were not.
6. **Audit:** Review correctness, input handling, dependency and secret exposure, security assumptions, regressions, performance, and reproducibility.
7. **Checkpoint:** Commit a coherent tested unit locally using a ticket reference. Push a branch only when appropriate; open a PR and review before merge.
8. **Record:** Update ticket notes, engineering ledger, relevant ADRs, and user-facing CHANGELOG only for externally meaningful changes. Close ticket only after acceptance criteria pass.

If any gate fails, return to the relevant earlier step; do not bypass checks to manufacture a passing status.

## Ticket states
Backlog → Ready → In Progress → Verification → Review → Done.
Blocked is an explicit state with reason, owner, and next action. Reopen a Done ticket only with evidence and link the regression.

## Definition of done
- Ticket requirements and acceptance criteria satisfied.
- Tests added or updated, and executed where tools are available.
- Correctness claims supported by witnesses/certificates or stated limitations.
- Security checklist and secret scan completed.
- Documentation, ledger, and ADRs updated where needed.
- Clean, reviewed commit with issue reference; no credentials or generated secrets.

## Commit policy
Use Conventional Commits and issue references: `feat(pcp): add residual transition validation (#12)`.
Commit at logical checkpoints, not every file save. Never commit failing intermediate states to `main`.
Commit timestamps are provided by Git. Avoid timestamp comments in source code; use dated decision records and structured experiment metadata instead.
