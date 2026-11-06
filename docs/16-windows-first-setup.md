# Windows-first setup — beginner-safe

The repository is **not created yet**. Follow these steps in PowerShell.

## 0. Install prerequisites
- Git for Windows: https://git-scm.com/downloads/win
- Rust + Cargo through rustup: https://rustup.rs/
- VS Code (optional): https://code.visualstudio.com/
- GitHub account and browser access.

Close and reopen PowerShell after installation. Check:
```powershell
git --version
rustc --version
cargo --version
```

## 1. Extract the ZIP
Download `ResolveX-Research-foundation-v0.2.zip` and extract it into your projects directory.
Open PowerShell inside the extracted `ResolveX-Research` folder.

```powershell
Get-Location
Get-ChildItem -Force
```

## 2. Fill in owner information
Replace `[COPYRIGHT HOLDER]` in `LICENSE`, and `REPLACE_WITH_*` fields in `CITATION.cff`.
Do not guess or invent author identity. Review `CONTRIBUTING.md` and `SECURITY.md`.

## 3. Run local checks
```powershell
cargo fmt --all -- --check
cargo test --workspace
cargo clippy --workspace --all-targets -- -D warnings
```
If a check fails, capture the exact output before making changes. These commands have **not** been verified in the packaging environment because Cargo was unavailable.

## 4. Create a public empty GitHub repository
On GitHub choose New repository, name `ResolveX-Research`, Public.
Do **not** initialize it with a README, license, or .gitignore; those files are already in the ZIP.
Copy your exact HTTPS repository URL.

## 5. Initialize Git locally
```powershell
git init -b main
git config user.name "YOUR NAME"
git config user.email "YOUR VERIFIED GIT EMAIL"
git status
git add .
git diff --cached --stat
git diff --cached --check
git commit -m "chore: initialize ResolveX research foundation (RX-001)"
git remote add origin https://github.com/YOUR_USERNAME/ResolveX-Research.git
git remote -v
git push -u origin main
```
Do not paste personal access tokens into chat, code, or commands. Use Git Credential Manager/browser authentication when prompted.

## 6. GitHub configuration
Repository Settings: enable Issues, Discussions, Wiki.
Add branch ruleset for `main`: PR required for future changes, CI required when stable, prevent force-push and deletion.
Create first Issue for RX-001 and subsequent tickets from `docs/13-ticketing-system.md`.
Review Actions output before declaring bootstrap complete.

## 7. First checkpoint
Record commit SHA using `git log -1 --format="%h %s"`.
Update `docs/12-engineering-ledger.md` and `internal/tickets/RX-001-repository-bootstrap.md` with actual evidence.

## 8. Development branch for next ticket
```powershell
git switch -c feat/RX-002-pcp-semantics
```
Create small commits, test, then push the branch and open a pull request.

**Stop after step 3 and share the command outputs if you want a guided verification before publishing.**
