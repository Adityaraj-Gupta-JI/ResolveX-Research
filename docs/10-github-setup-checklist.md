# First GitHub Setup Checklist

## Before publishing
- [ ] Replace `[COPYRIGHT HOLDER]` in LICENSE and README.
- [ ] Replace author placeholders in CITATION.cff; add repository URL only after it exists.
- [ ] Decide exact GitHub owner and repository name (`ResolveX-Research` proposed).
- [ ] Review all-rights-reserved terms; no open-source permissions are granted.
- [ ] Verify there are no secrets, private datasets, or unlicensed third-party assets.

## Create repository
- [ ] GitHub -> New repository -> name `ResolveX-Research` -> **Public**.
- [ ] Do not auto-add README/.gitignore/license if pushing this existing scaffold.
- [ ] Enable Issues, Discussions, Wiki and (optional) Projects in repository settings.
- [ ] Create Discussions categories: Research Questions, Mathematical Hypotheses, Formal Verification, Algorithms, Benchmarks, General.
- [ ] Create Wiki pages: Home, Getting Started, Mathematical Foundations, Formal Verification, Roadmap. Keep canonical documents in `/docs`.
- [ ] Configure branch protection/ruleset for `main` after first push; require passing CI and pull requests where practical.

## First push (PowerShell or Bash)
```bash
cd ResolveX-Research
git init -b main
git add .
git commit -m "chore: establish ResolveX research repository foundation"
git remote add origin https://github.com/OWNER/ResolveX-Research.git
git push -u origin main
```
Replace `OWNER` with your GitHub username/organization. If the repository was initialized remotely with commits, reconcile histories rather than forcing a push.

## Validation
```bash
cargo fmt --all -- --check
cargo clippy --workspace --all-targets -- -D warnings
cargo test --workspace
cargo run -p resolvex-cli
```
Expected CLI output: a scaffold notice; **no solver is implemented yet**.

## After first push
- [ ] Confirm CI completes successfully.
- [ ] Pin a discussion introducing the research questions and correctness rules.
- [ ] Create milestone `M0 — Mathematical Kernel` and corresponding issues.
- [ ] Verify GitHub displays CITATION.cff as expected after placeholder completion.
- [ ] Add repository description and topics from README.
- [ ] Record first architecture decisions in `docs/adr/`.
