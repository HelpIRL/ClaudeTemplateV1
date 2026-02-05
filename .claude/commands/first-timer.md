# First Timer

Onboard a new user to the Claude Template. Run once, then offer to self-remove.

## Instructions

Display this orientation:

---

**Welcome to the Claude Template**

You're set up. Here's the quick map.

### What Just Happened

BRAIN walked you through project setup:
- **Begin** — captured your idea
- **Refine** — clarified constraints
- **Arrange** — created intent structure

Your project is now configured in `CONTEXT.md`.

### Key Files

| File | Role |
|------|------|
| `CLAUDE.md` | AI behavior contract — rules Claude follows |
| `CONTEXT.md` | Your project structure and constraints |
| `.claude/commands/` | Slash commands you invoke |
| `.claude/skills/` | Behavioral patterns Claude applies automatically |
| `Intents/` | Where work gets broken down |

### Commands vs Skills

**Commands** = You invoke them (`/commit`, `/review`, `/brain`, `/status`)
**Skills** = Claude applies them when relevant (no action needed from you)

### What's Next

1. Describe what you want to build
2. Claude creates intent files under `Intents/`
3. Work through intents, commit at boundaries

### Learn More

- `.claude/README.md` — detailed docs on commands, skills, hooks
- `/status` — see current project state
- `/recap` — re-establish context after a break

---

## Cleanup

After displaying the orientation, ask the user:

> "This command is meant to run once. Want me to remove `/first-timer` from your commands folder to keep things tidy?"

If yes:
1. Delete `.claude/commands/first-timer.md`
2. Confirm: "Done. Happy building!"

If no:
1. Respond: "No problem — it'll be here if you need it. Happy building!"
