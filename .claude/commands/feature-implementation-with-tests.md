---
name: feature-implementation-with-tests
description: Workflow command scaffold for feature-implementation-with-tests in SP-MCP.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /feature-implementation-with-tests

Use this workflow when working on **feature-implementation-with-tests** in `SP-MCP`.

## Goal

Implements a new feature or endpoint, along with corresponding tests.

## Common Files

- `mcp_server.py`
- `plugin.js`
- `tests/run_tests.js`
- `tests/test_mcp_server.py`
- `tests/test_harness.js`
- `tests/live_inspect.py`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit or create implementation files (e.g., mcp_server.py, plugin.js)
- Update or create test files (e.g., tests/run_tests.js, tests/test_mcp_server.py, tests/test_harness.js, tests/live_inspect.py)
- Optionally update plugin.zip if the feature affects the plugin bundle

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.