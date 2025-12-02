## Context Persistence

Context persistence for agentic workflows.

## Quick Reference

- `/logical create <task>` - Start new task
- `/logical resume <task>` - Continue task
- `/logical update` - Sync progress (ongoing task)

## Workflow

```
plan → create → work → update → resume
```

## Structure

```
.logical/
└── <task>/
    ├── PLAN.md    # Static
    └── CONTEXT.md # Dynamic
```

Full command details: `.claude/commands/logical.md`
