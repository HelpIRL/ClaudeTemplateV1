# Project Context (Template)

⚠️ **This file is a template.** Follow the bootstrap instructions below.

Claude (and other AI tools) rely on this file to understand the project.
When this bootstrap section is present, the project has not been configured yet.

---

## Bootstrap Instructions for Claude

When you read this file and see this section, help the user set up their project
using the BRAIN method. Read `.claude/commands/brain.md` for full BRAIN details.

### Welcome Message

Display this to the user:

> **Welcome to BRAIN-assisted development.**
>
> The BRAIN method structures work into phases: **B**egin (capture the idea),
> **R**efine (clarify scope), **A**rrange (plan tasks), **I**terate (execute),
> **N**ext (decide what's next).
>
> **Your role:** You're the lead developer. You make decisions, set direction,
> and approve each phase. I help structure your thinking and execute the details.
>
> Each phase concludes with a git commit—clean rollback points for every step.

### Bootstrap Flow

1. **Auto-detect values**:
   - OWNER/REPO from `git remote get-url origin`
   - Existing folder structure

2. **Begin Phase**:
   - Ask: "What is this project? Give me the elevator pitch in 2-3 sentences."
   - Acknowledge receipt only—no analysis, suggestions, or reframing
   - Commit: `chore(init): begin project definition`

3. **Refine Phase** — Ask targeted questions:
   - Primary language/framework?
   - Build command? (or "none yet")
   - Test command? (or "none yet")
   - Source code location? (e.g., `src/`, `lib/`, project root)
   - Any key constraints or considerations?
   - Commit: `chore(init): refine project context`

4. **Populate Files**:
   - Replace this CONTEXT.md with real values (use template in next section)
   - Update `.github/ISSUE_TEMPLATE/config.yml`—replace `OWNER/REPO` with detected values
   - Commit: `chore(init): populate project configuration`

5. **Explain Task Workflow**:
   - "Your project is configured. Features are broken into tasks under `Tasks/`."
   - "Standard practice: commit when each task is complete so work is captured
     and you have clean rollback points."

6. **Transition**:
   - Ask if ready to scaffold their first feature
   - If yes, proceed with BRAIN Arrange phase for the feature

---

## CONTEXT.md Template (use this for replacement)

Once bootstrap is complete, replace this entire file with the following,
filled in with the user's answers:

```markdown
# Project Context

## Project Structure

- **Source code**: {location}
- **Tests**: {location or "none yet"}
- **Config files**: {list relevant files}
- **Generated artifacts**: {build outputs, or "none"}

## Language & Tooling

- **Language**: {language}
- **Framework**: {framework or "none"}
- **Build**: `{build command}` or "none yet"
- **Test**: `{test command}` or "none yet"
- **Package manager**: {npm, pip, cargo, etc. if applicable}

## Build & Test Entry Points

These are the approved commands. Do not invent alternatives.

- Build: `{command}`
- Test: `{command}`
- Lint: `{command}` (if applicable)

## Task Management

Tasks are stored under `Tasks/{FeatureName}/` with numbered task files.
See `.claude/commands/brain.md` for the BRAIN workflow.

## Constraints

{Any project-specific rules, limitations, or considerations the user mentioned}
```

---

End of bootstrap instructions. Once CONTEXT.md is replaced, this section is gone
and Claude will read the real project context instead.
