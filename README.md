## Implementation Notes

### Week 3 Progress (Jun 15)
**What I built:**
- Removed `docs/plugins/absubmit.rst` — AcousticBrainz service permanently shut down
- Removed `docs/plugins/acousticbrainz.rst` — same upstream shutdown
- Removed `docs/plugins/beatport.rst` — plugin deprecated
- Updated `docs/plugins/index.rst` — removed all references to the three deleted plugins from the toctree and description sections

**Challenges faced:**
- Confirmed Oppia required Python 3.10 which was incompatible with my Python 3.13.1, so switched to beets instead
- Used sed commands to cleanly remove plugin references from the index file

**Commits:**
- ba03515: docs: remove deprecated acousticbrainz, absubmit, and beatport plugins

**Branch:** https://github.com/Mo200227/beets/tree/fix-issue-5780
