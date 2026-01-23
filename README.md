# Claude Project Template

This repository is a **starter template** for projects that use AI-assisted development
with strong guardrails, repeatability, and auditability.

It is a **normal Git repository** with a small set of conventions that allow
AI tools (such as Claude) to work safely and predictably alongside humans.

---

## Maintainer & Contact

This project is maintained by **HelpIRL LLC**.

- 🌐 Website: https://helpirl.com
- 📧 Email: john@helpirl.com
- 🧑‍💻 GitHub: https://github.com/helpirl

For questions about:
- using this template
- AI-safe development workflows
- training or consulting

please reach out via email or open an issue.

## License

This project is licensed under the **MIT License**.

You are free to use, modify, and distribute this template, including for
commercial purposes. See the `LICENSE` file for details.

## What This Template Is

- A **human-first project scaffold**
- A **safe starting point** for AI-assisted coding
- A way to standardize:
  - documentation
  - task breakdown
  - commits
  - AI behavior

Nothing in this repo is required for your code to run.
If you remove all AI-related files, the project still works.

---

## Key Files

| File | Purpose |
|---|---|
| `README.md` | Human onboarding and project overview |
| `CONTEXT.md` | Project-specific structure and constraints (AI-first) |
| `CLAUDE.md` | AI behavior and guardrails |
| `commands/` | AI-invoked workflows (e.g. BRAIN) |
| `Tasks/` | Structured task breakdowns, grouped by feature |

---

## Typical Workflow

1. **Initialize a new project**
   - Use this repo as a template **or**
   - Run the initialization script in an existing repo

2. **Update `README.md`**
   - Replace this file with real project documentation
   - Describe what the project does and how humans use it

3. **Update `CONTEXT.md`**
   - Describe the actual project structure
   - Define build/test entry points
   - Document constraints that AI should not guess

4. **Work using Tasks**
   - Break work into feature folders under `Tasks/`
   - Each task is a small, self-contained unit of work
   - Git commits occur at task boundaries

5. **Let AI assist safely**
   - AI follows the rules in `CLAUDE.md`
   - Real-world actions go through approved tools
   - Humans review results, not shell commands

---

## Task Structure Example

