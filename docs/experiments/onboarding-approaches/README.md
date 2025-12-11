# Onboarding Approaches Test Matrix

**Status:** Experiment concluded (2025-12-11)

## Summary

Tested different ways for users to set up Claude-as-Coach skills. The **skill-creator approach** (fetch SKILL.md + package) was validated and promoted to the main [QUICKSTART.md](../../../QUICKSTART.md).

## Approaches Tested

| Approach | Result | Notes |
|----------|--------|-------|
| **Simple** (condensed skills) | Not tested | Removed - lower fidelity |
| **Complex** (full skills concatenated) | Not tested | Removed - too large |
| **Skill Creator** (fetch + package) | **SUCCESS** | Promoted to QUICKSTART.md |

## Results

### Skill Creator Approach (v2 - fetch SKILL.md + package)
- Date tested: 2025-12-10
- Tester: Zach
- Result: **SUCCESS**
- Notes:
  - Fetches SKILL.md content from GitHub (not .zip)
  - skill-creator packages each into .skill artifact
  - User downloads artifacts and uploads via Settings > Capabilities
  - project-coach-setup inlined (no fetch needed)
  - **Prerequisite:** User must have skill-creator installed first

## Current State

- **Primary onboarding:** [QUICKSTART.md](../../../QUICKSTART.md) (paste-and-go with skill-creator)
- **Fallback:** [QUICKSTART-MANUAL.md](../../../QUICKSTART-MANUAL.md) (manual download links)

## Known Issues

### .zip vs .skill Naming
- GitHub shows files as `.zip`
- Claude.ai UI may show `.skill`
- They're the same format
- Documented in QUICKSTART troubleshooting
