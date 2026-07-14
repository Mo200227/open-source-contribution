# Contribution #2: $EDITOR is not respected, likely due to uv virtualenv

**Contribution Number:** 2
**Student:** Mo200227
**Issue:** https://github.com/beetbox/beets/issues/6641
**Status:** Phase I Complete

---

## Why I Chose This Issue

This issue was recently marked as `good first issue` by maintainer @semohr who also approved the proposed solution. The fix involves adding an `editor` config option to beets so users can permanently set their preferred editor in `config.yaml` instead of relying on the `$EDITOR` environment variable which gets lost in virtualenv isolation.

---

## Understanding the Issue

### Problem Description
When beets is installed via pipx with the uv backend, the `$EDITOR` environment variable is not passed into the virtualenv. This means the `edit` plugin cannot find the user's preferred editor and falls back to `xdg-open`, which doesn't wait for the editor to close.

### Expected Behavior
Users should be able to set their preferred editor permanently in `config.yaml`:
```yaml
editor: nano
```

### Current Behavior
Beets only reads `$EDITOR` and `$VISUAL` environment variables, which are stripped by pipx's uv virtualenv isolation.

### Affected Components
- `beets/util/__init__.py` — where editor selection logic lives
- `docs/reference/config.rst` — where the new config option needs to be documented

---

## Reproduction Process

### Environment Setup
- beets 2.11.0 installed
- Python 3.13.1
- macOS

### Steps to Reproduce
1. Install beets via pipx with uv backend
2. Set `$EDITOR=nano` in shell
3. Run `beet edit <item>`
4. Observe that `$EDITOR` shows as `None` inside beets

---

## Solution Approach

### Implementation Plan

**Understand:** Beets reads `$EDITOR`/`$VISUAL` from environment variables. When installed via pipx/uv, these variables are stripped from the virtualenv environment.

**Match:** The editor selection logic is in `beets/util/__init__.py` in the `editor_command()` function. Similar config options exist for other settings throughout the codebase.

**Plan:**
1. Add an `editor` config option to `beets/util/__init__.py`
2. Modify `editor_command()` to check the config option first, then fall back to `$EDITOR`/`$VISUAL`
3. Document the new option in `docs/reference/config.rst`
4. Add a changelog entry in `docs/changelog.rst`
5. Write tests for the new behavior

**Review:** Follow `CONTRIBUTING.rst` standards

**Evaluate:** Run existing tests to confirm no regressions

---

## Testing Strategy

- [ ] Test that `editor` config option overrides `$EDITOR`
- [ ] Test that `$EDITOR` still works as fallback when config option not set
- [ ] All existing tests still pass

---

## Implementation Notes

*To be completed in Phase III*

---

## Pull Request

*To be completed in Phase IV*

---

## Learnings & Reflections

*To be completed at end of program*

---

## Resources Used

- Issue thread: https://github.com/beetbox/beets/issues/6641
- Beets contributing guide: https://github.com/beetbox/beets/blob/master/CONTRIBUTING.rst
