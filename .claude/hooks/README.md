# Claude Code Hooks

Hooks allow you to run scripts at specific points in Claude Code's workflow.

## Hook Types

| Hook | When it runs |
|------|--------------|
| `PreToolUse` | Before a tool executes (can block) |
| `PostToolUse` | After a tool completes |
| `UserPromptSubmit` | When user submits a prompt |

## Configuration

Hooks are configured in `.claude/settings.json`:

```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Edit|Write",
        "hooks": [
          {
            "type": "command",
            "command": ".claude/hooks/pre-edit.sh",
            "timeout": 5
          }
        ]
      }
    ]
  }
}
```

## Example: Block edits on main branch

Create `.claude/hooks/pre-edit.sh`:

```bash
#!/bin/bash
# Block edits on protected branches
branch=$(git branch --show-current 2>/dev/null)
if [[ "$branch" == "main" || "$branch" == "master" ]]; then
  echo '{"block": true, "message": "Cannot edit on protected branch. Create a feature branch first."}' >&2
  exit 2
fi
```

Make it executable: `chmod +x .claude/hooks/pre-edit.sh`

## Hook Response Format

Hooks can return JSON to control behavior:

```json
{"block": true, "message": "Reason for blocking"}
{"feedback": "Message shown to Claude"}
{"suppressOutput": true}
```

## Resources

- [Claude Code Hooks Documentation](https://code.claude.com/docs/en/hooks)
- [Example from ChrisWiles/claude-code-showcase](https://github.com/ChrisWiles/claude-code-showcase)
