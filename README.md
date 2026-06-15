# Contribution #1: docs: Identify and clean up references to broken or unmaintained plugins

**Contribution Number:** 1
**Student:** Mo200227
**Issue:** https://github.com/beetbox/beets/issues/5780
**Status:** Phase II Complete

---

## Why I Chose This Issue

I chose this issue because it is well-scoped and clearly defined — audit the beets plugin documentation, identify broken or unmaintained plugins, and clean up the docs accordingly. The task matches my current skill level since it involves reading documentation and Python codebases rather than complex new feature development.

---

## Understanding the Issue

### Problem Description
The beets documentation references many plugins, some of which are outdated, unmaintained, or no longer functional. This confuses users trying to find reliable tools.

### Expected Behavior
The plugin documentation should only reference actively maintained plugins, with dead links removed and the sidebar reorganized into categories.

### Current Behavior
The docs have a long alphabetical list of plugins including deprecated ones like `acousticbrainz` whose upstream service was shut down.

### Affected Components
- `docs/` folder — plugin documentation pages
- Plugin sidebar and index pages

---

## Reproduction Process

### Environment Setup
- Installed beets 2.11.0 via `pip3 install beets`
- Cloned fork locally: `git clone https://github.com/Mo200227/beets.git`
- Created working branch: `fix-issue-5780`
- beets version confirmed: 2.11.0, Python 3.13.1

### Steps to Reproduce
1. Go to https://beets.readthedocs.io/en/latest/plugins/
2. Observe the sidebar — it contains a very long alphabetical list of plugins
3. Click on `acousticbrainz` plugin — the upstream AcousticBrainz service was shut down, making this plugin non-functional
4. Click on `beatport` plugin — listed as deprecated, no longer works
5. **Expected:** Only active, maintained plugins should be listed
6. **Actual:** Deprecated and broken plugins are still listed with no indication they are non-functional

### Reproduction Evidence
- **Working branch:** https://github.com/Mo200227/beets/tree/fix-issue-5780
- **Confirmed broken plugins:** `acousticbrainz`, `absubmit` (AcousticBrainz shutdown), `beatport` (deprecated)
- **Issue comment with audit list:** https://github.com/beetbox/beets/issues/5780#issuecomment-3083262808

---

## Solution Approach

### Analysis
The root cause is that the docs were never updated when certain upstream services shut down or plugins became unmaintained. The `acousticbrainz` and `absubmit` plugins reference a service (AcousticBrainz) that was permanently shut down. The sidebar is also unsorted and too long.

### Proposed Solution
Work through the TODO list in the issue comments, research each plugin's current status, and:
1. Remove documentation for `acousticbrainz` and `absubmit` (upstream shutdown)
2. Remove or mark `beatport` as deprecated
3. Reorganize the sidebar to match the category structure on the main plugins page

### Implementation Plan

**Understand:** The beets docs list plugins alphabetically including ones that no longer work. Users have no way to know which are active.

**Match:** The issue comment already has a partial audit list started by the maintainer at https://github.com/beetbox/beets/issues/5780#issuecomment-3083262808

**Plan:**
1. Go through each plugin in the TODO list in the issue comments
2. For each plugin, check: Does the upstream service still exist? Is the repo still maintained? Does it work with current beets?
3. Update `docs/plugins/index.rst` to remove or mark broken plugins
4. Reorganize the sidebar in `docs/index.rst`
5. Delete `.rst` files for fully removed plugins

**Review:** Follow beets CONTRIBUTING.rst guidelines before submitting PR

**Evaluate:** Verify docs build correctly with `pip install sphinx` and `make html` in the docs folder

---

## Testing Strategy

- [ ] Verify docs build without errors after changes
- [ ] Confirm removed plugins are no longer listed in sidebar
- [ ] Check that all remaining plugin links are valid

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

- Issue thread: https://github.com/beetbox/beets/issues/5780
- Beets contributing guide: https://github.com/beetbox/beets/blob/master/CONTRIBUTING.rst
- Beets docs: https://beets.readthedocs.io/en/latest/plugins/
