<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Fluidise/.github/main/profile/assets/brand/logo-white.svg">
    <img src="https://raw.githubusercontent.com/Fluidise/.github/main/profile/assets/brand/logo.svg" alt="Fluidise logo" width="128" height="128">
  </picture>
</p>

<h1 align="center">Fluidise</h1>

<p align="center">
  <strong>The Developer Experience (DX) suite designed for AI agents and automated workflows.</strong><br>
  Deterministic, safe, standalone tools with zero runtime dependencies.
</p>

---

## Overview

Modern software development increasingly relies on autonomous AI coding agents, continuous integration pipelines, and automated bots. However, traditional developer experience tooling was built strictly for human terminal interaction—frequently producing unstructured logs, invoking hidden shell subprocesses, requiring bloated runtimes, or performing unexpected filesystem mutations.

**Fluidise** builds developer tools from the ground up with a strict **Agent-First** invariant: interfaces, outputs, and side-effects are designed primarily for programmatic consumption, automated decision-making, and high-reliability environments, while remaining ergonomic for human maintainers.

---

## Suite Components

### Available Now

* **[`fluidise-lint`](https://github.com/Fluidise/lint)** — *Standalone, deterministic commit-message validation.*
  * **Agent-First Schema**: Emits versioned, machine-readable JSON (`schema_version: 1`) by default on `stdout` with precise diagnostic spans. Human-readable text formatting is available via `--format text`.
  * **Conventional Commits**: Enforces Conventional Commits 1.0.0 with project-configurable rules via `fluidise.toml`.
  * **Strict Non-Mutation**: Never alters repository files, installs unannounced hooks, or runs network calls.
  * **Dual Interface**: Distributed as a standalone precompiled binary (macOS ARM64/x86_64, Linux) and as an embeddable Rust crate.
  * **Installation**: Available via the official Homebrew tap:
    ```sh
    brew tap Fluidise/homebrew-tap
    brew install fluidise-lint
    ```

---

### Planned & In Scoping

The following components are formally scoped under the Fluidise architectural roadmap and are actively being prepared:

* **Git Hook Manager**
  * A lightweight, predictable Git lifecycle orchestrator (`commit-msg`, `pre-commit`, `pre-push`) built as a standalone binary.
  * Designed to execute project-defined commands with bounded execution guarantees, explicit logging, and seamless agent ergonomics without requiring Node, Python, or Ruby environments.

* **GitHub-Side & CI Enforcement**
  * Server-side policy checks and pull-request verification workflows that bring Fluidise validation rules directly into GitHub CI and merge pipelines.
  * Ensures that automated pull requests and bot merges uphold repository standards before merge operations.

* **Shared Foundation (`fluidise.toml`)**
  * An optional, unified declarative configuration standard anchored at repository roots.
  * Allows all adopted Fluidise tools to share global project policies while preserving complete package independence (no tool requires the others to function).

---

## Core Guarantees

Every tool in the Fluidise suite adheres to four invariants:

1. **Agent-First & Deterministic**: Stable JSON output schemas, predictable exit codes (`0` for valid, `1` for invalid, `2` for operational errors), and bounded diagnostic aggregation.
2. **Zero Runtime Dependencies**: Shipped as native precompiled binaries. Adopters do not need to install Node, Bun, Python, JVM, or Rust toolchains to run Fluidise tools.
3. **Strict Safety & Isolation**: In-process execution with strict resource bounds. Tools do not trigger unannounced network requests, spawn arbitrary shell commands, or silently modify repository state.
4. **Standalone Modularity**: Every package is an autonomous building block. Adopting one tool never imposes the installation or adoption of the rest of the suite.

---

## Repositories

| Repository | Purpose | Status |
| --- | --- | --- |
| [**`Fluidise/lint`**](https://github.com/Fluidise/lint) | Standalone commit-message linter (CLI & Rust crate) | **Active (v0.1.0)** |
| [**`Fluidise/homebrew-tap`**](https://github.com/Fluidise/homebrew-tap) | Official Homebrew installation tap for macOS | **Active** |
| [**`Fluidise/core`**](https://github.com/Fluidise/core) | Shared foundation, product contracts, and brand identity | **Active** |

---

## Community & Contributing

Fluidise is developed as open source software for maintainers and automated environments. 

* All project specifications and public documentation are maintained in English.
* Core tools and distribution packages are licensed under the [MIT License](https://github.com/Fluidise/lint/blob/main/LICENSE).
