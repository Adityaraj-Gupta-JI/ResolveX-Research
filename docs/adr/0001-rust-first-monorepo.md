# ADR-0001 — Rust-first monorepo

**Status:** Accepted for scaffold.

## Decision
Use one Rust Cargo workspace for the core, PCP, termination, proof, benchmark, and CLI components. A web interface will consume the same engine through an API rather than duplicate mathematical logic.

## Rationale
Strong types, memory safety, modular tests, shared correctness boundaries, and reproducible CLI experiments.

## Consequences
A learning curve in Rust and explicit integration work for TLA+ and SMT tooling. No microservices in the initial architecture.
