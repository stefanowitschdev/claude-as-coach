# F39: Summary Skill Date Drift Fix

**Status:** Active - Implementation ready
**Effort:** Quick win (20-30 min)
**Priority:** High (affects daily workflow reliability)
**Source:** Week 8 retro (P1), Demo observations
**Created:** 2025-12-14

---

## Problem

Daily summary skill gets confused when run the next morning. The primary date gets confused between "today" (when skill runs) and the date being summarized (yesterday's events).

## Root Cause

The skill determines "today" from bash date verification but doesn't distinguish between:
- **Date being summarized** (yesterday's events)
- **Today's date** (when the skill runs)

## Scenario That Breaks

1. User has Monday's events to summarize
2. User runs "daily summary" Tuesday morning
3. Skill verifies: "Today is Tuesday"
4. Skill asks: "Which date's summary?"
5. User says: "Yesterday" (Monday)
6. **BUG:** Skill sometimes drifts back to Tuesday in later sections

## Example from Week 8

Friday Dec 12 summary was generated Saturday morning and contained "Friday, December 13" instead of "Friday, December 12".

## Desired Behavior

- Summary clearly identifies the date of the day being summarized
- Even if run at 7am the next morning, the summary is titled and framed as the previous day
- Ground truth section should anchor on the primary date explicitly

## Implementation

### Fix Required

1. Add explicit "SUMMARY_DATE" vs "TODAY" distinction throughout
2. Ground truth at document top = SUMMARY_DATE (already correct)
3. All subsequent references use SUMMARY_DATE, not "today"
4. Add reminder after date confirmation: "All references below are for [SUMMARY_DATE], not today."

### Suggested Additions to Skill

Add after date confirmation step:

```markdown
### 2a. Lock Summary Date

After confirming the summary date, establish it as the anchor:

**SUMMARY_DATE:** [Confirmed date, e.g., "Monday, December 15, 2025"]

All references in this document refer to SUMMARY_DATE, not today's date.

If running the next morning, remind yourself:
- TODAY = the day you're generating the summary
- SUMMARY_DATE = the day being summarized (the content)
- The document is ABOUT SUMMARY_DATE
```

### Files to Update

- `skills/daily-summary-base/SKILL.md` - Add explicit date tracking language

## Test Scenario

1. Tuesday morning, say "daily summary"
2. Confirm "Monday" as summary date
3. Complete entire summary
4. Verify: filename = Monday, all content references Monday, no Tuesday drift

## Success Criteria

- [ ] Skill explicitly distinguishes SUMMARY_DATE from TODAY
- [ ] Ground truth section shows SUMMARY_DATE
- [ ] No date drift in later sections when run next morning
- [ ] Test scenario passes
