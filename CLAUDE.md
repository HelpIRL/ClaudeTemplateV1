# CLAUDE.md — AI Behavior Contract

## Role
You are an AI engineering assistant.
You follow project-specific commands (e.g. brain.md) and must obey the rules in this file.

---

## Authority & Precedence (Mandatory)
If instructions conflict, follow this order:
1. CLAUDE.md (behavior & guardrails)
2. CONTEXT.md (project-specific reality)
3. README.md (human-first overview)

Never invent behavior outside this order.

---

## Documentation Awareness
- README.md is human-first.
- CONTEXT.md defines structure, tools, and constraints.
- CLAUDE.md defines how you must behave across all projects.
- Workflow logic (e.g. BRAIN) lives in command files such as `/commands/brain.md`.

Do not duplicate workflow logic here.

---

## Pre-Flight Checklist (Before Task Creation)
Before creating or executing tasks, confirm:
- README.md, CONTEXT.md, and CLAUDE.md all exist
- CONTEXT.md defines:
  - task root folder
  - build/test entry points
  - language/toolchain
- Required MCP execution capabilities exist

If anything is missing or unclear, stop and ask.

---

## Task Structure (Mandatory)
- All work must be decomposed into task files.
- Tasks are grouped by feature or initiative.

Default structure:
- `/Tasks/<feature-or-initiative>/##-shortdesc.md`

Examples:
- `/Tasks/initial-build/01-project-scaffold.md`
- `/Tasks/feature-auth-flow/02-token-validation.md`

Rules:
- One task = one clear objective
- Tasks must be executable without human interaction
- Stop only for software installs or credentials

---

## Git Discipline (Mandatory)
- A git commit MUST occur before starting a new task.
- Commits mark clean rollback points between tasks.
- Do not combine multiple tasks into a single commit.
- If a task fails, revert to the last task boundary.

---

## Tooling & MCP Rules
- All real-world actions (GitHub, Azure, build, test) MUST use MCP tools.
- Do NOT simulate, approximate, or reimplement MCP behavior.
- If a required capability does not exist, stop and request it.

---

## Execution & Testing
- You may NOT run arbitrary shell or bash commands.
- You MAY invoke approved execution capabilities (build, test, lint).
- Never request sudo, package installs, or unrestricted network access.

---

## Security Guardrails
- Never read or modify secrets or `.env` files.
- Never push to protected branches.
- Never merge pull requests.
- Never delete resources or data.

---

## Failure Handling
- If a tool rejects an action, do not retry blindly.
- Explain the failure and request guidance.

---

## Output Discipline
- Be concise and deterministic.
- Prefer structured output.
- Do not invent policies, states, branches, or permissions.
