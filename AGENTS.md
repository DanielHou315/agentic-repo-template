# AGENTS.md

## Repo Introduction

<fill in on setup>

## Repo Map

Where things live. Update when a top-level directory is added, moved, or removed.

| Path | Contents |
| --- | --- |
| `src/` | <fill in: application code> |
| `tests/` | <fill in: test suites, mirroring `src/`> |
| `scripts/` | <fill in: dev and maintenance scripts> |
| `docs/` | Concise, human-facing governance: conventions, architecture, decisions. Start at `docs/README.md`. |
| `docs/specs/`, `docs/plans/` | Agent working documents. Gitignored; do not link them as canonical. |
| `.envrc.example` | Every environment variable, with a comment. |
| `.worktrees/` | One git worktree per branch. Gitignored. |

**Ephemeral outputs are never committed:** caches, local DBs, uploads, agent scratch. Keep them gitignored.

## Commands

Only the commands needed to verify work. Everything else belongs in `docs/`.

```sh
<fill in>   # install / set up
<fill in>   # build
<fill in>   # run all tests
<fill in>   # run a single test
<fill in>   # lint + format
<fill in>   # run the app locally
```

## Environment

Environment via direnv. Local `.envrc` (gitignored, owner-managed) exports all variables.
`.envrc.example` is committed and lists every variable with a comment; add new variables there.
Never commit secrets. The root `.env` is deprecated.

## Working Together

- **Be honest.** Say what you actually did and what you verified. If tests fail, a step was skipped,
  or you are unsure, say so plainly. Never paper over a failure to look done.
- **Disagree openly.** If a request, plan, or existing rule looks wrong, say so and explain why
  before proceeding. Pushback is expected, not rude. Flattery and reflexive agreement are not useful.
- **Surface ambiguity instead of guessing.** When there are multiple reasonable interpretations,
  name them and ask, or pick one and state the assumption.
- **Stay in scope.** Do what was asked. Mention adjacent problems you notice; don't fix them unasked.
- **Leave the owner's words alone.** Don't rewrite human-authored docs or comments unless asked;
  suggest changes instead.

## Workflow

### Branches and worktrees

- **Branches** off `main`: `feat/*`, `fix/*`, `chore/*`, `docs/*`. Never commit on `main`. Each
  branch is a worktree at `.worktrees/<branch with / replaced by ->`; the repo root stays on `main`.
- **Parallel work** goes to subagents in separate worktrees on disjoint file sets. The main session
  owns git (branching, commits, merges). Each agent reports a ledger of the files it changed.

### Commits and pull requests

- **Commits:** `type(scope): imperative summary`, types `feat|fix|chore|docs|test|refactor`. Small
  and focused.
- **Pull requests.** When a branch is done and its tests pass, open a PR against `main`
  (`gh pr create`); merge only through the PR.
- **No AI attribution anywhere** — no "Generated with Claude Code", no "Co-Authored-By: Claude" in
  commits, PRs, or docs.

### Releases

- **Versioning.** PRs do not bump the version by themselves. Once a working prototype exists, adopt
  semver: a `VERSION` file at the repo root, a `CHANGELOG.md`, and version bumps as their own
  `chore(release): vX.Y.Z` PRs, each followed by a git tag and a GitHub release with the source
  (`gh release create`). No package builds in CI are required.

## Engineering Principles

1. **Think and design before coding.** State assumptions, surface tradeoffs, and ask when confused rather than
   silently picking an interpretation.
2. **Simplicity first.** Write the minimum code that solves the problem. No speculative features,
   abstractions for single uses, or configurability nobody asked for.
3. **Surgical changes.** Touch only what the task requires and match the surrounding style. Every
   changed line should trace back to the request. Clean up only the mess your own change created.
4. **Goal-driven, test-driven execution.** Turn the task into a verifiable goal (usually a failing
   test), then loop until it passes. "Done" means verified, not just written.
5. **Tests stay lean.** Remove unnecessary or unused tests as part of the change that makes them
   obsolete; the agent that touches a test area is responsible for its cleanup.

## Ask First

Confirm with the owner before:

- Destructive or history-rewriting git operations (force push, `reset --hard`, deleting branches
  that aren't yours).
- Adding, removing, or upgrading dependencies.
- Changing CI, release, or deployment configuration.
- Deleting data, migrations, or files you did not create.
- Anything that publishes outside the repo (PRs are fine; posting elsewhere is not).

## Where Rules Live

This file says *where* and *what is expected*. *How* lives in `docs/`, and applies to humans and
agents alike. Create these files when there is something to put in them:

- `docs/README.md` — index of the docs.
- `docs/architecture.md` — system overview, major components, data flow.
- `docs/conventions.md` — code style, naming, error handling, logging.
- `docs/testing.md` — test layout, fixtures, what to test and what not to.
- `docs/agents.md` — agent-specific workflow detail (subagent briefs, worktree mechanics, ledgers).
- `docs/decisions/` — short records of non-obvious decisions and why.

When rules conflict: the owner's direct instruction, then this file, then `docs/`.

## Maintaining This File

Keep it short; every line costs context in every session. Add a line only when its absence caused
a mistake or a wasted search. Prefer a pointer into `docs/` over an explanation here. Agents may
propose edits; the owner approves them.
