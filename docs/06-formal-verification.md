# Formal Verification Plan — v0.1

## Goal
Write abstract TLA+ specifications for PCP residual transitions and restricted-program execution, then check representative finite models with TLC. Introduce Apalache or SMT-backed obligations where justified.

## PCP properties
- Nonempty match requirement.
- Canonical residual transition preserves concatenation difference.
- Witness reconstruction agrees with original tile words.
- Rejected branches are prefix-incompatible.

## Termination properties
- Interpreter transitions respect the specified operational semantics.
- Finite-state models preserve relevant invariants.
- Candidate ranking functions meet decrease and lower-bound obligations under assumptions.

## Critical limits
A bounded model check is not proof of arbitrary PCP UNSAT. A TLA+ specification does not automatically prove a Rust program conforms to it. A verified candidate invariant must be inductive under the stated transition relation.

## Planned workflow
Mathematical definition -> TLA+ state variables/actions -> invariants -> finite model checking -> Rust implementation -> conformance tests -> independent proof checking.

## Status
No `.tla` specification has been authored or model-checked in this scaffold. Add actual formal models only after semantics are reviewed.
