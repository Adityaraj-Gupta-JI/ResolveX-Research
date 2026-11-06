# Product Requirements Document — v0.1

## Users and jobs
- Student: create a problem, observe transitions, understand the limits of search.
- Researcher: define an instance family, compare algorithms, inspect evidence, export reproducible experiments.
- Formal-methods practitioner: inspect specifications, assumptions, invariants and proof artifacts.

## Product modules
1. **PCP Explorer:** tile editor, validation, search, residual-state graph, solution witness verification.
2. **Termination Explorer:** restricted-language editor, transition semantics, loop analysis, ranking functions, recurrent sets.
3. **Proof Inspector:** independent witness/certificate validation and explicit verification status.
4. **Benchmark Laboratory:** parameter sweeps, at least ten benchmark categories, raw-data export, charts with labeled units.
5. **Research Notebook:** hypotheses, counterexamples, experiment references, citations.

## Primary user flow
Choose engine -> enter instance -> set assumptions and limits -> run analysis -> inspect states -> verify proposed conclusion -> export results and provenance.

## Priorities
P0: Rust CLI, typed input/result models, PCP witness search and independent verification, restricted termination semantics, foundational TLA+ models.
P1: browser UI, state graph, benchmark runner, proof/certificate formats, research export.
P2: SMT-backed synthesis, AI-assisted heuristics, advanced visualizations and proof-assistant integration.

## Out of scope for MVP
Universal PCP decision; arbitrary Rust-program termination; treating AI confidence as proof; cloud accounts and payments.

## Acceptance criteria
- Every supported input validates or returns a structured error.
- Positive PCP witnesses are replayed by an independent checker.
- Negative PCP conclusions are issued only with a sound certificate or mathematically complete finite exploration.
- Timeouts and inconclusive analysis return UNKNOWN.
- Termination claims explicitly state the initial-state domain and arithmetic semantics.
- All benchmark charts derive from stored experiment measurements.
