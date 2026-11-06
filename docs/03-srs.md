# Software Requirements Specification — v0.1

## Result semantics
PCP results: `SAT`, `UNSAT`, `UNKNOWN`. `SAT` requires a nonempty tile-index sequence with equal concatenations; `UNSAT` requires sound proof evidence; bounded non-discovery is `UNKNOWN`.

Termination results should distinguish `TERMINATES`, `NONTERMINATES`, and `UNKNOWN` **under explicit initial-state assumptions**. Do not conflate existence of one diverging execution with universal nontermination.

## Functional requirements
- FR-001 Parse and validate finite PCP tile lists and nonempty solution sequences.
- FR-002 Explore canonical prefix-compatible residual transitions with configurable budgets.
- FR-003 Produce and independently check PCP witnesses.
- FR-004 Support only explicitly defined sound negative certificates.
- FR-005 Parse a restricted imperative language with mathematical integer semantics.
- FR-006 Explore finite transition models and test candidate ranking/invariant conditions.
- FR-007 Store solver results separately from verification results.
- FR-008 Cancel jobs and enforce time/state/memory budgets where feasible.
- FR-009 Export versioned instances, solver configuration, metrics and artifacts.
- FR-010 Execute at least ten distinct reproducible benchmark categories.
- FR-011 Display graph and plot data with axes, units and provenance.

## Nonfunctional requirements
Determinism for fixed seeds; safe Rust where feasible; testable components; local-first execution; versioned schemas; CI checks; reproducible benchmarking; accessibility and no color-only status cues.

## Planned data model
`ProblemInstance`, `AnalysisConfig`, `RunRecord`, `CandidateResult`, `VerificationRecord`, `Certificate`, `MetricSeries`.

## Verification gate
A candidate proof is never displayed as verified until the independent checker has accepted it. A checker failure is an error, not a successful result.

## Constraints
A TLA+ model check does not by itself verify the Rust implementation. Resource-limited checking must not be presented as a universal theorem.
