## Phase III — Build ✅

**What I built:**
- Modified `beets/util/__init__.py` line 941 — `editor_command()` function
- Added `editor` config option check before `$VISUAL`/`$EDITOR`
- Function now checks `config["editor"]` first, then falls back to environment variables

**Commit:** 8c40ebe — feat: add editor config option to editor_command()

**Branch:** https://github.com/Mo200227/beets/tree/fix-issue-6641
