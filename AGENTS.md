<!--
SPDX-FileCopyrightText: 2026 SAP SE or an SAP affiliate company and Autonomous Operations contributors

SPDX-License-Identifier: Apache-2.0
-->

# AGENTS Guidelines

## Writing standards

- US English. Plain language as most contributors are not native speakers.
- Active voice and present tense.
- One idea per sentence, 20 words or fewer.
- Use MUST / MUST NOT / SHOULD / MAY (RFC 2119) for requirements.
- Same term for the same concept throughout.
- No filler: "please note that", "it is worth mentioning", "as you can see."
- Define abbreviations on first use.

## Security

- No hardcoded credentials, tokens, or secrets of any kind.
- No plaintext secrets in configuration files, runbooks, or comments.

## Version control

- Branch naming: `feat/<description>`, `chore/<description>`, `fix/<description>`, `release/<version>`.
- No direct commits to `main`.
- Do not use `--no-verify` to bypass pre-commit hooks.
