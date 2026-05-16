```markdown
# SP-MCP Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the core development patterns, coding conventions, and workflows used in the SP-MCP repository. The project is primarily Python-based (with some JavaScript), and organizes work around clear, repeatable workflows for feature development, task tracking, and plugin deployment. By following these patterns, you can contribute effectively and maintain consistency across the codebase.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `mcpServer.py`, `pluginZipBuilder.js`

### Import Style
- Use **relative imports** in Python.
  - Example:
    ```python
    from .utils import parseConfig
    ```

### Export Style
- Use **named exports** in JavaScript.
  - Example:
    ```js
    export function startServer() { ... }
    export const PLUGIN_VERSION = "1.0.0";
    ```

### Commit Messages
- Follow **Conventional Commits** with prefixes:
  - `feat`, `conductor`, `chore`, `fix`, `docs`
- Example commit message:
  ```
  feat: add plugin manifest validation to build process
  ```

## Workflows

### Feature Implementation with Tests
**Trigger:** When adding a new feature or endpoint  
**Command:** `/new-feature`

1. Edit or create implementation files (e.g., `mcp_server.py`, `plugin.js`)
2. Update or create corresponding test files:
    - `tests/run_tests.js`
    - `tests/test_mcp_server.py`
    - `tests/test_harness.js`
    - `tests/live_inspect.py`
3. If the feature affects the plugin bundle, update `plugin.zip`
4. Commit your changes with a descriptive conventional commit message

**Example:**
```python
# mcp_server.py
def new_feature():
    pass  # implementation here

# tests/test_mcp_server.py
def test_new_feature():
    assert new_feature() is not None
```

---

### Conductor Task or Phase Completion
**Trigger:** When completing a planned task or phase in a development track  
**Command:** `/complete-task`

1. Edit the relevant plan file: `conductor/tracks/<track>/plan.md`
2. Mark the task or phase as complete (e.g., check off a checkbox or update status)
3. Commit with a `conductor:` or `chore:` prefix

**Example:**
```markdown
<!-- conductor/tracks/api/plan.md -->
- [x] Implement authentication endpoint
- [ ] Document API usage
```

---

### Conductor Track Archive
**Trigger:** When a development track is finished and needs archiving  
**Command:** `/archive-track`

1. Move track files (`index.md`, `metadata.json`, `plan.md`, `spec.md`) to `conductor/archive/<track>/`
2. Update `conductor/tracks.md` to reflect the archive
3. Commit with a `conductor:` or `chore:` prefix

**Example:**
```bash
mv conductor/tracks/api/* conductor/archive/api/
# Edit conductor/tracks.md to remove 'api' from active tracks
```

---

### Plugin ZIP Rebuild
**Trigger:** After updating code or configuration that affects the deployable plugin  
**Command:** `/rebuild-plugin`

1. Update code or config files as needed (`plugin.js`, `manifest.json`, `icon.svg`)
2. Rebuild or update `plugin.zip` with the latest changes
3. Commit with a `chore:` or `feat:` prefix

**Example:**
```bash
zip plugin.zip plugin.js manifest.json icon.svg
```

## Testing Patterns

- **Framework:** Unknown (tests found in both Python and JavaScript)
- **File Pattern:** Test files use `*.test.ts` (TypeScript), but also `test_*.py` and `test_*.js`
- **Typical Structure:**
    - Place tests in the `tests/` directory
    - Name test files after the module being tested

**Example:**
```python
# tests/test_mcp_server.py
def test_server_startup():
    assert start_server() == True
```

```js
// tests/test_harness.js
import { startServer } from '../plugin.js';
test('server starts', () => {
  expect(startServer()).toBeTruthy();
});
```

## Commands

| Command          | Purpose                                                      |
|------------------|--------------------------------------------------------------|
| /new-feature     | Start a new feature or endpoint with corresponding tests     |
| /complete-task   | Mark a conductor task or phase as complete                   |
| /archive-track   | Archive a completed conductor track                          |
| /rebuild-plugin  | Rebuild or update the plugin.zip bundle after changes        |
```
