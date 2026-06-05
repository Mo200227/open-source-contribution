# Contribution #1: Add field for developer-supplied notes for feature flags

**Contribution Number:** 1
**Student:** Mo200227
**Issue:** https://github.com/oppia/oppia/issues/19610
**Status:** Phase I Complete

---

## Why I Chose This Issue

I chose this issue because it involves Python backend work, which aligns with 
my programming experience from CS1302. The task is well-scoped and clearly 
defined: add a `developer_notes` field to the feature flag specification in 
the Oppia codebase and display it in the Release Coordinator UI.

I'm interested in this issue because it involves both backend (Python) and 
frontend (HTML/TypeScript) work, giving me exposure to a full-stack change 
in a real production codebase. The issue has detailed comments from previous 
contributors showing exactly which files need to change, which will help me 
navigate an unfamiliar codebase for the first time.

---

## Understanding the Issue

### Problem Description

The Oppia platform has "feature flags" that developers can toggle on/off 
in the Release Coordinator page. Currently, there is no way for developers 
to leave notes for admins explaining what a flag does or what steps to take 
when toggling it.

### Expected Behavior

Each feature flag should have an optional `developer_notes` field that is 
hardcoded by developers in the backend. When this field is non-empty, it 
should be displayed in the Release Coordinator UI so admins can see 
important instructions.

### Current Behavior

Feature flags have no notes field. Admins have no way to know if special 
steps are required when toggling a flag.

### Affected Components

- `core/domain/feature_flag_domain.py` — add `developer_notes` to FeatureFlagSpec
- `core/templates/pages/release-coordinator-page/features-tab/features-tab.component.html` — display notes in UI
- `core/templates/pages/release-coordinator-page/features-tab/features-tab.component.ts` — update component logic
- Related test files

---

## Reproduction Process

*To be completed in Phase II*

---

## Solution Approach

*To be completed in Phase II*

---

## Testing Strategy

*To be completed in Phase III*

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

- Issue thread: https://github.com/oppia/oppia/issues/19610
- Oppia contributing wiki: https://github.com/oppia/oppia/wiki/Contributing-code-to-Oppia
