# Template Update

Update this project's base template files from the upstream source.

## Source Repository

```
https://github.com/HelpIRL/ClaudeTemplateV1
Branch: main
```

## What Gets Updated

These files are **safe to update** (generic, not project-specific):

- `CLAUDE.md` — AI behavior contract
- `.claude/commands/*.md` — Slash command definitions

## What Does NOT Get Updated

These files are **project-specific** and will NOT be modified:

- `README.md` — Your project documentation
- `CONTEXT.md` — Your project structure and constraints
- `.claude/settings.json` — Your permission and hook configuration
- `.github/*` — Your issue templates and workflows
- Any other existing files

## Instructions

1. Fetch the latest template files from the upstream repository using raw GitHub URLs:
   ```
   https://raw.githubusercontent.com/HelpIRL/ClaudeTemplateV1/main/CLAUDE.md
   https://raw.githubusercontent.com/HelpIRL/ClaudeTemplateV1/main/.claude/commands/<name>.md
   ```

2. Get the list of command files from the template repo:
   ```bash
   gh api repos/HelpIRL/ClaudeTemplateV1/contents/.claude/commands --jq '.[].name'
   ```

3. For each updatable file:
   - Fetch the latest version from template repo
   - Compare with local version
   - If different, show a brief summary of changes
   - Update the file

4. For `.claude/commands/`:
   - Update existing command files that match template names
   - Add any new command files from the template
   - Do NOT delete local command files missing from template (user may have custom commands)
   - Do NOT update this file (`template-update.md`) to avoid mid-execution issues

5. Report summary:
   - Files updated
   - Files skipped (no changes or not in template)
   - New files added
