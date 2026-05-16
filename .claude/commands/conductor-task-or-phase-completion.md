---
name: conductor-task-or-phase-completion
description: Workflow command scaffold for conductor-task-or-phase-completion in SP-MCP.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /conductor-task-or-phase-completion

Use this workflow when working on **conductor-task-or-phase-completion** in `SP-MCP`.

## Goal

Marks tasks or phases as complete in the conductor planning system.

## Common Files

- `conductor/tracks/*/plan.md`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit conductor/tracks/<track>/plan.md to mark task or phase as complete

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.