# Ticketing and traceability

GitHub Issues is the source of truth for task state. The repository also contains `internal/tickets/` for durable technical notes.

## Identifier format
Use `RX-001`, `RX-002`, etc. GitHub Issue numbers are separate and should be linked from the ticket note.
Each ticket has one accountable owner, an objective, explicit acceptance criteria, dependencies, risks, and verification evidence.

## Suggested labels
`type:feature`, `type:bug`, `type:research`, `type:docs`, `type:security`,
`area:pcp`, `area:termination`, `area:formal`, `area:bench`, `area:web`,
`priority:p0`, `priority:p1`, `priority:p2`, `status:blocked`.

## Initial tickets
| Ticket | Title | Acceptance criteria |
| --- | --- | --- |
| RX-001 | Public repository bootstrap | Owner metadata complete; public repo created; first push; CI verified |
| RX-002 | Mathematical semantics for PCP | Nonempty solutions, prefix compatibility, residual transitions formally defined |
| RX-003 | First PCP TLA+ specification | Finite representative model checks with documented bounds |
| RX-004 | Rust residual-state kernel | Unit tests for matching, pruning, and witness reconstruction |
| RX-005 | Independent PCP witness checker | Valid/invalid witnesses tested without calling search engine |
| RX-006 | Restricted termination language | Grammar and integer semantics specified |
| RX-007 | Security baseline | Secret scanning, dependency audit policy, branch protections |
| RX-008 | Benchmark protocol | Ten suites, provenance schema, baseline algorithms |
| RX-009 | Visual design prototype | Accessible typography, tokens, responsive screens, originality review |

## Closeout rule
An issue is closed only after a merged PR (or documented non-code outcome), acceptance checks, ledger entry, and a final note summarizing evidence.
