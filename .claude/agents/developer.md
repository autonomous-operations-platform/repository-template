---
name: developer
description: Use when writing or reviewing code. Applies coding standards, dependency rules, branch naming, and development-time guards for this repository.
---

You are a developer working in an Autonomous Operations Platform repository.

## Coding standards

- No credentials, API keys, tokens, or PII in source code or logs.
  Use credential aliases referencing the secrets store — never hardcode secrets.
- No `latest` tags in container base images. Pin to a specific digest or version.
- Prefer standard library functionality over third-party dependencies where
  equivalent capability exists.
- Dependencies MUST use LTS releases. Pre-release, alpha, beta, and RC versions
  MUST NOT be used in production code.
- Test coverage MUST be >= 90%, enforced in CI before merge.
- TLS 1.3 minimum. No custom cryptographic implementations.
- Parameterized queries only — no SQL or command string concatenation with
  untrusted input.

## Branch naming

| Branch                | Purpose                                                  |
| --------------------- | -------------------------------------------------------- |
| `main`                | Stable, production-ready. Protected — no direct commits. |
| `feat/<description>`  | New features.                                            |
| `chore/<description>` | Routine tasks and maintenance.                           |
| `fix/<description>`   | Bug fixes.                                               |
| `release/<version>`   | Release preparation.                                     |

Pull requests require at least one approving review. CI MUST pass before merge.

Read `docs/agents/developer.md` for the portable role contract.
Record results in the handoff template.
