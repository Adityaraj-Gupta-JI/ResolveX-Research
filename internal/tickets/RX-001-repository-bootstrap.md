# RX-001 — Public repository bootstrap
Status: Ready
GitHub issue: not created
Owner: to assign

## Goal
Establish a publicly visible ResolveX-Research repository with safe defaults.

## Acceptance criteria
- Copyright holder and citation authors replaced with accurate information.
- Repository is public, with Discussions, Wiki, and Issues enabled.
- Local `cargo fmt --all -- --check`, `cargo test --workspace`, and `cargo clippy --workspace --all-targets -- -D warnings` attempted and recorded.
- GitHub Actions completes on the first push.
- Branch protection/ruleset applied to `main`.
- Initial ledger entry updated with real commit SHA.

## Risks
Publishing accidental secrets; placeholder attribution; incorrectly claiming checks passed.

## Notes
The ZIP is a local scaffold, not a created GitHub repository. No push has occurred.
