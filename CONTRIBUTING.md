# Contributing to Fluidise

Thank you for your interest in contributing to Fluidise!

Fluidise creates the Developer Experience (DX) suite designed specifically for AI agents, automated workflows, and maintainers.

## Core Invariants

All contributions across the Fluidise organization must uphold our four architectural guarantees:

1. **Agent-First & Deterministic**: Output schemas must be machine-readable (stable JSON format), exit codes must follow deterministic conventions (`0` for success, `1` for invalid input, `2` for operational failure), and side effects must be bounded.
2. **Zero Runtime Dependencies**: Tools must ship as standalone precompiled binaries or modular native crates without requiring Node, Python, Ruby, or JVM runtime installations on user systems.
3. **Strict Safety & Isolation**: In-process execution with strict resource bounds. Tools must never perform surprise network calls, execute undocumented shell subprocesses, or mutate repository files without explicit commands.
4. **Standalone Modularity**: Every package is an autonomous building block. Adopting one component never forces adopting the entire suite.

## Development Workflow

### Git Branches & Worktrees

- We preserve `main` as the source of truth.
- Develop all features, fixes, and documentation in dedicated branches or git worktrees:
  - `feat/<short-name>`
  - `fix/<short-name>`
  - `docs/<short-name>`
  - `chore/<short-name>`

### Commit Conventions

Fluidise strictly adheres to the **Conventional Commits 1.0.0** specification.

- Format: `<type>(<scope>): <short description>`
- Common types: `feat`, `fix`, `docs`, `style`, `refactor`, `perf`, `test`, `build`, `ci`, `chore`.
- Use the imperative mood in the subject line (e.g. `add`, `fix`, `update`, not `added` or `fixes`).
- Validate commit messages locally using [`fluidise-clint`](https://github.com/Fluidise/clint):
  ```sh
  echo "feat(profile): add community guidelines" | fluidise-clint
  ```
- Do not include co-author metadata or trailing bot attribution lines in commit messages.

### Pull Requests

1. Open pull requests against the `main` branch.
2. Fill out the pull request template completely.
3. Ensure all CI checks (commit message validation and link integrity checks) pass cleanly.
4. Maintainers will review your PR and provide actionable, structured feedback.

## Code of Conduct

Fluidise is committed to providing a welcoming, constructive, and harassment-free environment for everyone, human and autonomous contributors alike.
