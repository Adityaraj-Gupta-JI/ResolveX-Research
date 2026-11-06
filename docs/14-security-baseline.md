# Security baseline

**Security is a continuing process, not a promise of zero vulnerabilities.** Never claim software is vulnerability-free.

## Secrets
- Never commit tokens, private keys, credentials, local `.env` files, or actual user data.
- Use environment variables or OS-managed secret stores for optional external integrations.
- Do not put secrets in browser bundles, screenshots, logs, test fixtures, or ticket notes.
- If leaked, revoke/rotate immediately; deleting a file from a later commit is insufficient.
- Use `git status`, `git diff --cached`, and a secret scanner before pushes.

## Dependencies and CI
- Prefer a small dependency graph; pin or lock versions as appropriate.
- Commit `Cargo.lock` for the workspace's executable applications.
- Run `cargo fmt`, `cargo clippy`, `cargo test`, and dependency/security review.
- Add `cargo audit` and `cargo deny` as separately installed CI tools when configured; do not claim they are active yet.
- Use minimal GitHub Actions permissions; pin third-party actions to trusted versions or commit SHAs after review.
- Restrict `main` using GitHub rulesets and required CI checks.

## Runtime
- Treat imported PCP instances, program text, experiment files, and uploaded content as untrusted.
- Enforce parser limits, timeouts, cancellation, and memory/resource budgets.
- Avoid arbitrary shell execution, unsafe deserialization, unrestricted file paths, and untrusted executable plugins.
- Keep Rust engine authoritative; browser visualizations do not determine mathematical correctness.
- Local server binds to loopback by default; use authentication before any remote exposure.

## Disclosure
Use `SECURITY.md` to coordinate reports; do not disclose sensitive exploit details in public Issues.
