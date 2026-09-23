# AGENTS.md

## Repo Introduction

<fill in on setup>

## Workflow Rules

1. **Branches** off `main`: `feat/*`, `fix/*`, `chore/*`, `docs/*`. Never commit on `main`. Each
   branch is a worktree at `.worktrees/<branch with / replaced by ->`; the repo root stays on `main`.
2. **Commits:** `type(scope): imperative summary`, types `feat|fix|chore|docs|test|refactor`. Small
   and focused. **No AI attribution anywhere** — no "Generated with Claude Code", no
   "Co-Authored-By: Claude" in commits, PRs, or docs.
3. **Environment via direnv.** Local `.envrc` (gitignored, owner-managed) exports all variables.
   `.envrc.example` is committed and lists every variable with a comment; add new variables there.
   Never commit secrets. The root `.env` is deprecated.
4. **Docs.** `docs/` is concise, human-facing governance. `docs/specs/` and `docs/plans/` are agent
   working documents and are gitignored; do not link them as canonical.
5. **Parallel work** goes to subagents in separate worktrees on disjoint file sets. The main session
   owns git (branching, commits, merges). Each agent reports a ledger of the files it changed.
6. **Ephemeral outputs are never committed:** caches, local DBs, uploads, agent scratch. Keep them gitignored.
7. **Pull requests.** Work is test-driven. When a branch is done and its tests pass, open a PR
   against `main` (`gh pr create`); merge only through the PR. PR descriptions carry no AI attribution.
8. **Tests stay lean.** Remove unnecessary or unused tests as part of the change that makes them
   obsolete; the agent that touches a test area is responsible for its cleanup.
9. **Versioning.** PRs do not bump the version by themselves. Once a working prototype exists, adopt
   semver: a `VERSION` file at the repo root, a `CHANGELOG.md`, and version bumps as their own
   `chore(release): vX.Y.Z` PRs, each followed by a git tag and a GitHub release with the source
   (`gh release create`). No package builds in CI are required.
