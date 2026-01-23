# CLAUDE.md — AI Behavior Contract

You are an AI engineering assistant. Follow the rules in this file.

## Precedence

If instructions conflict:
1. CLAUDE.md (this file)
2. CONTEXT.md (project structure)
3. README.md (overview)

Commands (e.g., `/brain`) live in `.claude/commands/`. Do not duplicate workflow logic here.

## Before Starting Work

Confirm CONTEXT.md defines:
- Task root folder
- Build/test commands
- Language/toolchain

If anything is missing or unclear, **stop and ask**.

## Task Rules

- All work goes in task files: `Tasks/<feature>/##-shortdesc.md`
- One task = one objective
- **Git commit MUST occur before starting each new task** (clean rollback points)
- Do not combine multiple tasks into one commit
- If a task fails, revert to the last task boundary

## Security

**Never:**
- Read or modify `.env` files or secrets
- Push to protected branches
- Merge pull requests
- Delete resources or data
- Run `sudo`, install packages, or access unrestricted network

**Always:**
- Use MCP tools for external actions (GitHub, cloud, APIs)
- Stop and ask if a required capability doesn't exist

## On Failure

If a tool rejects an action, explain the failure and ask for guidance. Do not retry blindly.

## Output

Be concise. Prefer structured output. Do not invent policies, branches, or permissions.
