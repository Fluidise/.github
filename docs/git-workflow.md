# Git Workflow & Commit Policy

This document defines the authoritative Git workflow, commit conventions, and repository standards across the [Fluidise](https://github.com/Fluidise) organization.

---

## 1. Branching & Isolation Policy

- **Main Branch (`main`)**: Protected source of truth. Direct commits or forced pushes to `main` are prohibited.
- **Feature & Task Branches**: Every modification must be developed in a dedicated branch or worktree:
  - `feat/<topic>`: New capabilities or tools.
  - `fix/<topic>`: Defect and bug fixes.
  - `docs/<topic>`: Documentation, guides, and specifications.
  - `ci/<topic>`: Automation workflows, CI pipelines, and GitHub actions.
  - `chore/<topic>`: Maintenance, hygiene, and tooling updates.
- **Git Worktrees**: For complex multi-branch work, prefer isolated worktrees located in `.worktrees/<branch-name>` to avoid workspace contamination.

---

## 2. Commit Message Standards

Fluidise enforces **Conventional Commits 1.0.0** on all repositories.

### Format

```text
<type>(<scope>): <description>

[optional body]

[optional footer(s)]
```

### Types

- **`feat`**: A new user- or agent-facing feature.
- **`fix`**: A bug fix.
- **`docs`**: Documentation updates only.
- **`style`**: Changes that do not affect code meaning (white-space, formatting).
- **`refactor`**: Code changes that neither fix a bug nor add a feature.
- **`perf`**: Code changes that improve performance.
- **`test`**: Adding missing tests or correcting existing tests.
- **`build`**: Changes that affect the build system or external dependencies.
- **`ci`**: Changes to CI configuration files and automation scripts.
- **`chore`**: Housekeeping, hygiene, or configuration maintenance.

### Enforcement

Commit messages are validated locally and in CI using **[`fluidise-clint`](https://github.com/Fluidise/clint)**:

```bash
# Validate commit message input directly
echo "docs(governance): add security and contributing policies" | fluidise-clint --format text
```

### Rules & Invariants

1. **Imperative Mood**: Use lowercase, concise imperative summaries (`add`, `update`, `fix`, not `added`, `updates`, `fixes`).
2. **No Trailing Periods**: The subject line must not end with a period.
3. **No Co-Author Attributions**: Do not include `Co-authored-by:` trailers in commit messages.
4. **Signatures**: Maintainers and contributors should configure SSH/GPG signing (`git config commit.gpgsign true`).

---

## 3. Pull Request Guidelines

1. **Atomic Commits**: Group related changes into logical, self-contained commits.
2. **Review & Gates**: Every pull request must pass automated validation gates before merging.
3. **Merge Strategy**: Rebase-and-merge or squash-and-merge depending on repository policy, maintaining a linear history.
