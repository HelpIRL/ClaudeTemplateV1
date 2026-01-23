# Claude Command: BRAIN Method — Project Skeleton & Task List

#

# Copyright (c) 2025 John Hewitt ([john@helpirl.com](mailto:john@helpirl.com))

# Licensed under the MIT License. See LICENSE file for details.

#

> **Purpose:** Create a minimal, consistent folder + file scaffold for an idea using the **BRAIN** method, then help convert it into an actionable, time‑boxed task list.

---

## BRAIN (concise & enforced)

* **Begin (B)** — **100% Human**
  Capture the spark fast (≤3 min). Dump raw thoughts, goals, constraints.

  > **Behavioral rule:** During **Begin**, Claude must **only acknowledge receipt** of the idea.
  > No analysis, no summarization, no suggestions, no reframing.

* **Refine (R)** — **90% Human**
  In ≤15 min, clarify scope, assumptions, success criteria, risks, resources.

  > Claude’s role is limited to asking **targeted clarifying questions** only.

* **Arrange (A)** — **90% AI (proposal only)**
  Draft a **proposed** breakdown of work into **≤2‑hour** tasks, numbered, with dependencies.

  > All Arrange output is **provisional** until explicit human approval.

* **Iterate (I)** — **90% AI**
  Execute tasks one at a time. Log outcomes, blockers, and actuals. Improve incrementally.

* **Next (N)** — **100% Human**
  Decide the very next action: next task, different project, pause, or add to TTDs.

---

## Defaults

* **Base path**: `Tasks/`
* **Folder name**: PascalCase derived from the idea title (stop‑words removed).
  Example: “figure out how to talk to AI” → `MyGreatFeature`
* **Task files**: `N.ShortName.md` (e.g., `01.ResearchAPIs.md`)
* **Task time**: 30 minutes
* **Never** overwrite existing files. Append and continue numbering.

**Example target shape**:

```
Tasks/
  MyGreatFeature/
    CONTEXT.md        # Begin + Refine
    01.SomeTask.md     # Arrange output (after approval)
    Status.md         # Iterate + tracking
```

---

## What to create

### 1. `{Base}/{IdeaFolder}/CONTEXT.md`

Begin + Refine live together in this file.

* Title, brief purpose
* **Begin**: raw notes (unaltered)
* **Refine**: structured clarification

```md
# {IdeaTitle}

> Owner: {Name}  ·  Created: {YYYY-MM-DD}  ·  Updated: {YYYY-MM-DD}

## Begin (raw)
<!-- 3-minute brain dump. Do not edit or reinterpret. -->

## Refine (scope)
- **Goal**:
- **In / Out of scope**:
- **Assumptions**:
- **Constraints**:
- **Definition of Done (DoD)**:
- **Risks / Mitigations**:
- **Resources** (people, docs, APIs, repos):
- **Dependencies**:
- **Rough Milestones**:
```

---

### 2. `{Base}/{IdeaFolder}/Status.md`

Tracks execution state and progress.

```md
# Status — {IdeaTitle}

## Iterate checklist (per work session)
- [ ] Pick next task
- [ ] Set a 2-hour timer
- [ ] Mid-session check (~75%) — continue / split / park
- [ ] Log outcome in task file
- [ ] Update table and decide Next

## Tasks
| No. | Name | Status | Est. | Actual | Notes |
|---:|---|---|---:|---:|---|
| 1 | … | Todo | 2h |  |  |

> **Ownership rules**:
> - Claude may update **Status** (Todo / In‑Progress / Blocked)
> - Human owns **Actual Time** unless explicitly provided

## Paused / Abandoned
- **State**: Active | Paused | Abandoned
- **Reason**:
- **Date**: YYYY-MM-DD
- **Revisit trigger (if paused)**:

## Links
- [CONTEXT.md](./CONTEXT.md)
- Task files listed above
```

---

### 3. Task files (created **only after Arrange approval**)

`N.ShortName.md`

```md
# {N}. {ShortName}

**Goal**:
**Est.**: ≤2 hours
**Prereqs / Dependencies**:

## Steps
- [ ] …

## Definition of Done
- [ ] …

## Notes
…

## Outcome (fill after Iterate)
- **Actual Time**:
- **Result**:
- **Follow-ups**:
```

---

## Safety & versioning rules

* Prefer **small, incremental changes**.
* Never delete or rename files without explicit approval.
* Never overwrite `CONTEXT.md`. If a rewrite is requested, back it up as `CONTEXT.v{n}.md`.
* If in a git repo, commit at each phase with clear messages:

  * `chore(brain): scaffold MyGreatFeature`
  * `feat(arrange): propose tasks 1–5`

---

## Inputs

* **IdeaTitle** (required)
* **BasePath** (optional; default `Tasks/`)
* **OpenAfterCreate** (optional; default `CONTEXT.md`)

### Derivations

* **IdeaFolder** = PascalCase(IdeaTitle, stop‑words removed)
* **ShortName** = 2–4 words, PascalCase, 3–24 chars, no punctuation

---

## Claude — Required execution order

1. **Confirm**: Echo `IdeaTitle`, `BasePath`, `TaskTime`, derived `IdeaFolder`.
2. **Create folders**: Ensure `{BasePath}/{IdeaFolder}/` exists.
3. **Create or append `CONTEXT.md`**:

   * If missing: create from template
   * If present: prepend new Begin/Refine sections with date tag
4. **Refine interview**:

   * Ask **3–5 questions max per turn**
   * Map each question to a missing Refine bullet
   * Allow `TBD` answers
5. **Propose Arrange list**:

   * 5–10 tasks
   * ≤ `{TaskTime}` each
   * Include brief DoD + dependencies
   * **Do not create files yet**
6. **Wait for approval** (explicit yes or edits)
7. **Create task files**:

   * Continue numbering from highest existing N
8. **Create / update `Status.md`**
9. **Open file**: `{BasePath}/{IdeaFolder}/{OpenAfterCreate}`
10. **Report**: Short summary of changes + suggested Next

---

## Idempotency

* If scaffold exists, append only.
* Never renumber existing tasks.
* Never infer approval.

---

## Quick start (copy/paste)

> **Do**: Create a BRAIN scaffold using this spec.
> **IdeaTitle**: "${YOUR_IDEA_TITLE}"
> **BasePath**: `Tasks/`
> **OpenAfterCreate**: `CONTEXT.md`

*Then follow the execution order above exactly.*
