# Contributing to ResolveX

Thank you for your interest in the research. This repository is **public but all rights reserved**; it is not offered under an open-source license.

## Ways to participate now

- Open an **Issue** for a reproducible defect, missing test, or documentation inconsistency.
- Start a **Discussion** for a mathematical question, research hypothesis, or benchmark proposal.
- Link relevant literature, with citation details and a short original summary.
- Report potential unsoundness, including counterexamples and exact reproduction steps.

## Code and content contributions

**Do not open a pull request containing code, documentation, figures, datasets, or other copyrightable material without prior written agreement with the maintainer about permissions and ownership.** A public repository and an invitation to discuss do not confer a license to submit or reuse code. Opening an issue or discussion does not transfer your copyright.

Maintainers should agree on contribution terms and third-party dependencies before enabling external pull requests. There is currently no Contributor License Agreement or automatic rights transfer.

## Research and correctness standards

1. Define the mathematical input domain and assumptions.
2. Explain the claimed property and whether it is proven, tested, or conjectured.
3. Supply a minimal reproducible case for a bug or a proof sketch for a mathematical claim.
4. Do not infer UNSAT from bounded search exhaustion.
5. Report benchmark machine details, seeds, timeouts, units, and raw data.
6. Distinguish solver output from independently verified conclusions.

## Development conventions (for authorized contributors)

Use short-lived topic branches, focused commits, `cargo fmt`, `cargo clippy`, and `cargo test --workspace`. Changes to mathematical semantics require updated tests and formal-specification review.

## Conduct

Be respectful, challenge claims with evidence, and avoid publishing private information or unlicensed third-party materials. The maintainer may moderate discussions and close unsupported or inappropriate submissions.
