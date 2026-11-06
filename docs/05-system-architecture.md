# System Architecture — v0.1

## Design
A single Rust Cargo workspace provides analysis, proof checking, benchmarks, and CLI. A future local Axum API serves a React/TypeScript research interface. SQLite is a possible later local experiment store; not required for the initial CLI.

```text
Web UI / CLI
      |
Input parser + configuration
      |
Core orchestration
      +--> PCP engine
      +--> Termination engine
      |
Candidate result -> Independent checker -> Verified / Failed / Unknown
      |
Experiment provenance -> plots / report export
```

## Crate responsibilities
- `resolvex-core`: shared models, result contracts, budgets.
- `resolvex-pcp`: PCP transition relation and search algorithms.
- `resolvex-termination`: restricted-language interpreter and termination analysis.
- `resolvex-proof`: certificate and witness checking independent of search heuristics.
- `resolvex-bench`: workloads, measurement and export.
- `resolvex-cli`: stable headless entry point.

## Key architecture decisions
ADR-001: Rust-first monorepo.
ADR-002: Three-valued epistemic PCP result statuses.
ADR-003: Formal specifications and implementation conformance are distinct obligations.
ADR-004: Public repository, all rights reserved.

## Interfaces to define next
JSON input schema, solver progress events, proof object format, benchmark record format, cancellation and resource-limit semantics.
