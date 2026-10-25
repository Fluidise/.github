# Security Policy

Fluidise takes security seriously. We build developer tools for automated agentic environments, and ensuring the integrity, isolation, and safety of these workflows is paramount.

## Supported Repositories & Versions

Security updates are provided for the latest active release of each component within the [Fluidise](https://github.com/Fluidise) organization:

| Component | Supported Version | Status |
| :--- | :--- | :--- |
| [`Fluidise/clint`](https://github.com/Fluidise/clint) | `>= 0.1.0` | Active |
| [`Fluidise/homebrew-tap`](https://github.com/Fluidise/homebrew-tap) | `HEAD` | Active |
| [`Fluidise/core`](https://github.com/Fluidise/core) | `HEAD` | Active |
| [`.github`](https://github.com/Fluidise/.github) | `HEAD` | Active |

## Reporting a Vulnerability

If you discover a potential vulnerability in any repository across the Fluidise organization, please do not report it through public GitHub issues or discussions.

Instead, please report vulnerabilities via one of the following channels:

1. **GitHub Private Vulnerability Reporting (Recommended):** Use the "Report a vulnerability" button under the **Security** tab of the affected repository.
2. **Direct Contact:** Email our security maintainers at `security@fluidise.com` (or contact maintainers directly via repository owner profiles) with the subject `[SECURITY] <Vulnerability Brief>`.

### Report Details

To help us triage and resolve the issue quickly, please include:

- Name and version of the affected tool or repository.
- Detailed steps to reproduce the vulnerability or a minimal reproduction scenario.
- Expected behavior vs. observed behavior.
- Potential impact and threat model (e.g. privilege escalation, sandbox escape, file mutation).

### Response Timetable

- **Acknowledgment:** Within 48 hours of report submission.
- **Initial Assessment:** Within 5 business days with preliminary triage.
- **Coordination & Disclosure:** We practice coordinated vulnerability disclosure (CVD). A patch and security advisory will be published together once the resolution is verified.
