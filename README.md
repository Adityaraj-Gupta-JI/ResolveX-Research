# ResolveX

**Proof-Guided Analysis of Correspondence Problems and Program Termination**

*Explore the Unknown. Prove the Possible.*

> **Status:** Research foundation / pre-implementation. The solver engines, formal specifications, and benchmark results are **not yet implemented or validated**. This repository is a public, all-rights-reserved research project; public visibility does not grant an open-source license.

## Overview

ResolveX is a planned research workbench combining two related but distinct computational domains:

1. **Post Correspondence Problem (PCP):** Explore finite tile systems using residual-state search, sound pruning, independently checked solution witnesses, and eventually sound proof certificates for selected negative cases.
2. **Program termination:** Analyze a precisely defined restricted imperative language using transition systems, ranking functions, invariants, and recurrent sets.

The project aims to integrate a Rust computational kernel, TLA+ specifications, reproducible benchmark experiments, and an interactive scientific visualization interface. It **does not** claim to decide arbitrary PCP instances or the general Halting Problem.

## Research objective

Investigate whether proof-guided symbolic abstractions and invariant discovery can improve the practical classification and analysis of selected correspondence and termination problems compared with established baselines.

A result must distinguish **SAT / UNSAT / UNKNOWN** for PCP. Any claimed SAT or UNSAT outcome requires a separately checked witness or sound certificate. For program termination, conclusions must state their assumptions and the scope of initial states.

## Planned system

```text
Input -> Validation -> Rust analysis engine -> Independent checking
                                               -> Results & provenance
                                               -> Benchmarks & visualizations
```

| Component | Planned role |
| --- | --- |
| `crates/resolvex-core` | Shared types, resource limits, results |
| `crates/resolvex-pcp` | PCP transitions, search and pruning |
| `crates/resolvex-termination` | Restricted-language semantics and analysis |
| `crates/resolvex-proof` | Independent proof and witness checking |
| `crates/resolvex-bench` | Reproducible experimental runner |
| `crates/resolvex-cli` | Local command-line entry point |
| `formal/tla` | TLA+ abstract specifications |
| `apps/web` | Future interactive research workbench |
| `docs` | Product, system and research specifications |
| `research` | Hypotheses, literature and experiments |

## Getting started (foundation only)

Install the stable Rust toolchain and Cargo. From the repository root:

```bash
cargo fmt --all -- --check
cargo test --workspace
cargo run -p resolvex-cli
```

The CLI currently prints a scaffold notice. It does not solve problems yet. TLA+, TLC, Apalache, Z3 and the web UI will be introduced as implementation milestones, not as prerequisites for this initial scaffold.

## Documentation

Start with [Project Vision](docs/01-project-vision.md), [PRD](docs/02-prd.md), [SRS](docs/03-srs.md), [Mathematical Foundations](docs/04-mathematical-foundations.md), [Architecture](docs/05-system-architecture.md), [Formal Verification](docs/06-formal-verification.md), [Benchmark Methodology](docs/07-benchmark-methodology.md), [Testing](docs/08-testing-strategy.md), and [Roadmap](docs/09-roadmap.md).

See [GitHub Setup Checklist](docs/10-github-setup-checklist.md) for repository settings and the first push.

## Research integrity

- A bounded search that finds no witness does **not** prove a general PCP instance has no solution.
- TLA+ model checking is not a universal undecidability solver or automatic proof of Rust implementation correctness.
- Machine-learning predictions, visual patterns, and performance plots are not mathematical certificates.
- Report UNKNOWN when resource limits are reached or proof checking is inconclusive.
- Never present synthetic or illustrative benchmark values as measured findings.

## Community and contributions

Discussions and issues are welcome for research questions, reproducible bug reports, and suggestions. **Do not submit code or other copyrightable material in a pull request unless the project maintainer has explicitly approved the contribution terms.** Read [CONTRIBUTING.md](CONTRIBUTING.md).

## Citation

Citation metadata is provided in [CITATION.cff](CITATION.cff) with placeholders that must be completed by the repository owner before formal citation or release. No paper, DOI, or publication is claimed.

## Copyright and rights

Copyright (c) 2026 [COPYRIGHT HOLDER]. **All rights reserved.** See [LICENSE](LICENSE). No permission to use, copy, modify, or distribute the code is granted by the public availability of this repository.

## Engineering governance and design

See [Development Workflow](docs/11-development-workflow.md), [Engineering Ledger](docs/12-engineering-ledger.md), [Ticketing](docs/13-ticketing-system.md), [Security Baseline](docs/14-security-baseline.md), [Visual Design Direction](docs/15-design-direction.md), [Windows Setup](docs/16-windows-first-setup.md), and [Visualization Protocol](docs/17-visualization-research.md).

The initial reference posters are inspiration only and are **not** redistributed with this repository.
