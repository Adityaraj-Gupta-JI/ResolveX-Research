# Engineering ledger

This append-only log records **why work was performed**, its evidence, and its relationship to tickets and commits.
It is internal-facing engineering documentation stored in the public repository: **never include credentials, private personal information, security exploit details, or confidential discussions**.

Unlike `CHANGELOG.md` (user-visible release changes), this ledger records engineering decisions, blockers, verification evidence, and reversals.

| Date (UTC) | Ticket | Decision/change | Evidence | Commit/PR | Follow-up |
| --- | --- | --- | --- | --- | --- |
| 2026-11-06 | RX-000 | Established public research foundation and iterative verification workflow | Foundation package v0.2; runtime compilation pending | Not yet committed | Configure GitHub, verify Rust toolchain |

## Entry template
- Date/time (UTC):
- Ticket:
- Objective and scope:
- Prior state / reason:
- Files or modules changed:
- Design decision and alternatives:
- Tests and formal checks run (with exact outcomes):
- Security review:
- Commit / PR / issue links:
- Known limitations and next actions:

Do not rewrite historical entries to conceal mistakes. Add a dated correction referencing the original entry.
