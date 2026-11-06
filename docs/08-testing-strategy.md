# Testing Strategy — v0.1

## Layers
1. Rust unit tests for parsing, residual transitions and operational semantics.
2. Property-based tests for invariants and canonicalization.
3. Differential tests against a simple reference implementation on small instances.
4. Independent witness/certificate replay.
5. TLA+ model checks on explicitly bounded finite instances.
6. Integration tests from CLI input to structured output.
7. Regression corpus for previously discovered counterexamples.
8. Benchmark validation for repeatability and metric units.

## Must-have adversarial tests
Empty index sequence rejection; empty words if permitted by chosen PCP convention; no-prefix-compatible branch; repeated residuals; bounded search exhaustion; integer overflow mismatch; false ranking functions; nontermination counterexamples; resource cancellation.

## CI
The initial workflow checks formatting, Clippy and Rust unit tests. Formal model checking is not yet integrated.
