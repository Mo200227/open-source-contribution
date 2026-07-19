## Phase II — Reproduce & Plan ✅

### Environment Setup
- beets 2.11.0 installed, Python 3.13.1
- Cloned fork locally at ~/beets
- Branch: fix-issue-6641

### Key File Found
- `beets/util/__init__.py` line 941 — `editor_command()` function

### Current Code
```python
def editor_command() -> str:
    return (
        os.environ.get("VISUAL") or os.environ.get("EDITOR") or open_anything()
    )
```

### Implementation Plan
1. Add `editor` config option check before `$VISUAL`/`$EDITOR`
2. Update `editor_command()` in `beets/util/__init__.py`
3. Document new option in `docs/reference/config.rst`
4. Add changelog entry
5. Write tests

### Branch
https://github.com/Mo200227/beets/tree/fix-issue-6641
