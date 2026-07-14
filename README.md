# Contribution #1: docs: Identify and clean up references to broken or unmaintained plugins

**Contribution Number:** 1
**Student:** Mo200227
**Issue:** https://github.com/beetbox/beets/issues/5780
**Status:** Phase IV Complete

---

## Why I Chose This Issue

I chose this issue because it is well-scoped and clearly defined — audit the beets plugin documentation, identify broken or unmaintained plugins, and clean up the docs accordingly.

---

## Phase I — Issue Selection ✅

- Selected beets issue #5780
- Forked beetbox/beets to Mo200227/beets
- Created Contribution README repo
- Claimed issue in CodePath Slack

---

## Phase II — Reproduce & Plan ✅

- Installed beets 2.11.0 via `pip3 install beets`
- Cloned fork locally
- Created branch `fix-issue-5780`
- Identified broken plugins: acousticbrainz, absubmit, beatport
- Wrote UMPIRE-based solution plan

---

## Phase III — Build ✅

- Deleted `docs/plugins/absubmit.rst`
- Deleted `docs/plugins/acousticbrainz.rst`
- Deleted `docs/plugins/beatport.rst`
- Updated `docs/plugins/index.rst` removing all references
- Added changelog entry to `docs/changelog.rst`
- **Commit:** ba03515 — 4 files changed, 218 deletions
- **Branch:** https://github.com/Mo200227/beets/tree/fix-issue-5780

---

## Phase IV — Submit & Iterate ✅

- **PR:** https://github.com/beetbox/beets/pull/6778
- Wrote professional PR description referencing issue #5780
- Added changelog entry after bot feedback
- Tagged maintainer @snejus
- Maintainer @semohr engaged and provided feedback

**Maintainer Feedback:** semohr noted the issue was more complex than expected and suggested picking a different good first issue for Cycle 2. Encouraged continued contribution.

**Status:** Awaiting merge / moving to Cycle 2

---

## Resources Used

- Issue: https://github.com/beetbox/beets/issues/5780
- PR: https://github.com/beetbox/beets/pull/6778
- Branch: https://github.com/Mo200227/beets/tree/fix-issue-5780
