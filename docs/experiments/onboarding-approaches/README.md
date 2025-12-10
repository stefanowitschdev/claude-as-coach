# Onboarding Approaches Test Matrix

Testing different ways for users to set up Claude-as-Coach skills.

## The Problem

Current onboarding (QUICKSTART.md) requires:
1. Download 5 .zip files
2. Navigate to Settings > Capabilities > Skills
3. Upload each file
4. Create project
5. Start using

This is clunky. Can we simplify?

## Three Approaches to Test

| Approach | File | Lines | Method | Fidelity |
|----------|------|-------|--------|----------|
| **Simple** | `bootstrap-simple.md` | ~250 | skill-creator packages | Condensed |
| **Complex** | `bootstrap-complex.md` | ~1270 | skill-creator packages | Full |
| **Skill Creator** | `bootstrap-skill-creator.md` | ~60 | skill-creator packages | Exact |

### 1. Bootstrap Simple (`bootstrap-simple.md`)

- Condensed version of all 5 skills
- User pastes into fresh project chat
- Says "use skill-creator to package these"
- Claude creates .zip artifacts
- User uploads artifacts as skills

**Pros:** Single paste, no external downloads
**Cons:** Relies on skill-creator, skills may differ from originals

### 2. Bootstrap Complex (`bootstrap-complex.md`)

- Full concatenation of all 5 skills (~1270 lines)
- Same flow as Simple
- Higher fidelity to original skill content

**Pros:** Full skill content preserved
**Cons:** Large paste, still relies on skill-creator

### 3. Bootstrap Skill Creator (`bootstrap-skill-creator.md`)

- Fetches SKILL.md content from GitHub raw URLs
- skill-creator packages each into downloadable artifact
- User uploads via Settings > Capabilities

**Pros:** Exact skill fidelity, always up-to-date from repo
**Cons:** Requires skill-creator installed first, Settings navigation

## How to Test

### Test Protocol

1. Create fresh Claude.ai project
2. Use one approach to set up skills
3. Say "set up my project"
4. Verify project-coach-setup-base triggers
5. Complete setup flow
6. Test "good morning" (morning routine)
7. Test "daily summary" (daily summary)

### Success Criteria

- [ ] Skills install correctly
- [ ] Trigger phrases work
- [ ] Skill behavior matches originals
- [ ] User confusion is minimal

### Questions to Answer

1. Does skill-creator actually work for packaging skills from markdown?
2. Do condensed skills behave the same as full skills?
3. Which approach has lowest friction for new users?
4. How much does .zip vs .skill naming confuse users?

## Known Issues

### .zip vs .skill Naming Confusion

- GitHub shows files as `.zip`
- Claude.ai UI may show `.skill`
- They're the same format
- May confuse users who see both

**Mitigation:** Note this in documentation, explain they're equivalent.

## Results

### Skill Creator Approach (v1 - fetch .zip files)
- Date tested: 2025-12-10
- Tester: Zach
- Result: **PARTIAL SUCCESS**
- Notes:
  - GitHub raw URL fetches succeeded (all 5 .zip files)
  - Could NOT convert fetched binary data into downloadable artifacts
  - Falls back to manual download links (same friction as QUICKSTART.md)
  - Duplication issue: project-coach-setup was both inlined AND fetched

### Skill Creator Approach (v2 - fetch SKILL.md + package)
- Date tested: 2025-12-10
- Tester: Zach
- Result: **SUCCESS**
- Notes:
  - Updated to fetch SKILL.md content (not .zip)
  - skill-creator successfully packages each into .skill artifact
  - User downloads artifacts and uploads via Settings > Capabilities
  - Removed duplication (project-coach-setup inlined only, not fetched)
  - **Prerequisite:** User must have skill-creator installed first

### Simple Approach
- Date tested: Not yet tested
- Tester:
- Result:
- Notes:

### Complex Approach
- Date tested: Not yet tested
- Tester:
- Result:
- Notes:

## Recommendation

**Use bootstrap-skill-creator.md (v2 - fetch SKILL.md + package)**

**Pros:**
- Fetches fresh SKILL.md content from GitHub (always up to date)
- skill-creator packages into downloadable artifacts
- Reduces friction vs manual download links (artifacts in conversation)
- Project setup can begin immediately (inlined skill)

**Cons:**
- Requires skill-creator to be installed first (chicken-egg problem for new users)
- Still requires Settings > Capabilities upload step

**For Dec 12 demo:**
- Ensure skill-creator is installed before demo
- Paste bootstrap-skill-creator.md content
- Download 4 skill artifacts, upload, continue with setup
