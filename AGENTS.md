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

## Sub-agents

For tasks that require a focused persona, invoke a sub-agent from `.claude/agents/`:

| Sub-agent | When to invoke |
| --- | --- |
| `developer` | Writing or reviewing code |
| `architect` | Design decisions, ADRs, cross-component changes |
| `security-reviewer` | Pre-merge security review and compliance verification |
| `code-reviewer` | Structured code review before merge |
| `threat-modeler` | New components or data flows at design time |
| `devils-advocate` | Challenging a plan or design before committing to it |

### Workflows

#### Bug fix

```text
developer → code-reviewer → security-reviewer
```

#### New feature

```text
architect (plan) → developer → code-reviewer → security-reviewer
```

#### New component or service

```text
architect → threat-modeler → developer → code-reviewer → security-reviewer
```

#### Architecture decision

```text
architect → devils-advocate → architect (revise)
```

#### Documentation

```text
technical-writer (standalone, or after architect)
```

`security-reviewer` is always the last step before merge for agentic changes.
