# /logical $ARGUMENTS

Context persistence system. Tasks stored at `.logical/<task>/`.

## Usage

- `/logical create <task>` - New task with PLAN.md + CONTEXT.md
- `/logical resume <task>` - Continue from task context
- `/logical update` - Sync CONTEXT.md for ongoing task

## create <task>

1. `mkdir -p .logical/<task>`
2. Create PLAN.md:

```markdown
# <task>

Created: [date]

## Goal

[1-2 sentences]

## Phases

1. [Phase 1 name]
2. [Phase 2 name]
3. [Phase 3 name]

## Files

- [key files]

## Constraints

- [constraints]

## Success Criteria

- [criteria]
```

3. Create CONTEXT.md:

```markdown
# Context

Updated: [timestamp]

## Status

Active | Paused | Blocked | Complete

## Current Phase

[number] - [name]

## Completed

- [items]

## In Progress

- [items]

## Next

- [items]

## Blockers

- [items or "None"]

## Key Decisions

- [items]
```

4. Begin Phase 1

## resume <task>

1. Read `.logical/<task>/PLAN.md` and `CONTEXT.md`
2. Continue from "In Progress" / "Next"
3. No re-planning unless blocked

## update

1. Find ongoing task from current session
2. If none found, return "No active task"
3. Update `.logical/<task>/CONTEXT.md` with current state and timestamp

## Rules

- PLAN.md: Write once, reference only
- CONTEXT.md: Update at meaningful changes
- Delete `.logical/<task>/` when complete
