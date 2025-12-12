# FEATURE: Synthetic Demo Data System

**Status:** Planning
**Effort:** Medium (4-6 hours)
**Priority:** Medium - Supports demo reliability
**Related:** FEATURE-presentation-prep.md, examples/rob-the-runner/

## Problem Statement

Current synthetic demo data has gaps that cause friction during live demos:

1. **Run-day-only coverage:** Rob's C25K schedule generates Mon/Wed/Fri summaries, leaving Tue/Thu/Sat/Sun empty
2. **Brittle demo day alignment:** If demo day is Friday, "yesterday" (Thursday) has no summary
3. **Skills assume daily data:** Morning routine expects "yesterday's summary" to exist
4. **Real workflows don't have gaps:** Personal daily practice logs every day, so these edge cases don't surface until demo time

## Goals

1. **Skill resilience:** Skills gracefully handle missing data (good UX for all users, not just demos)
2. **Demo reliability:** Synthetic data supports any demo day without manual gap-filling
3. **Realistic rest days:** Rest day summaries exist with appropriate content (sleep, recovery, life)

## Two Tracks

### Track A: Skill Resilience (Priority)

Update skills to handle missing "yesterday" gracefully:

**Morning Routine:**
```
Current: Looks for yesterday's summary, fails silently or awkwardly if missing
Better: "No summary for yesterday. Last summary was [date]. Want a quick catch-up?"
```

**Weekly Retro:**
```
Current: Expects 7 daily summaries
Better: Works with available days, notes gaps in analysis
```

**Benefits:**
- Better UX for real users who miss days
- Demo works even with imperfect data
- More forgiving onboarding experience

### Track B: Synthetic Data Completeness

Expand `regenerate_demo_dates.py` to generate full daily coverage:

**Current templates (scenario-4):**
- W9-D1 (Monday, run day)
- W9-D2 (Wednesday, run day)
- W9-D5 (Friday, run day)

**Needed templates:**
- W9-D2 (Tuesday, rest day)
- W9-D4 (Thursday, rest day)
- W9-D6 (Saturday, optional)
- W9-D7 (Sunday, retro/planning day)

**Rest day summary content:**
- Sleep quality and duration
- Recovery notes (soreness, energy)
- Non-running activities
- Life context (work, family, etc.)
- Brief (shorter than run-day summaries)

## Implementation Tasks

### Phase 1: Skill Resilience
- [ ] Update `daily-morning-routine-base` to handle missing yesterday
- [ ] Update `retrospective-base` to work with partial week data
- [ ] Test edge cases: 1 day, 3 days, 7 days of data
- [ ] Document expected behavior in skill files

### Phase 2: Rest Day Templates
- [ ] Create rest-day summary template structure
- [ ] Write W9 rest day content for Rob (Tue, Thu, Sat)
- [ ] Update `regenerate_demo_dates.py` to handle rest days
- [ ] Add `--include-rest-days` flag (or make default)

### Phase 3: Demo Day Flexibility
- [ ] Add `--ensure-yesterday` flag to regenerate script
- [ ] Script calculates which days must exist for demo day
- [ ] Validates generated output has required coverage
- [ ] Error if template missing for required day

### Phase 4: Scenario Alignment
- [ ] Audit each scenario for demo requirements
- [ ] Document which demos work with which scenarios
- [ ] Update scenario READMEs with "works on [days]" guidance

## Demo Day Requirements Matrix

| Demo | Requires | Scenario 2 | Scenario 4 |
|------|----------|------------|------------|
| Morning Routine | Yesterday's summary | Partial | Partial |
| Daily Summary | Context docs | Yes | Yes |
| Weekly Retro | 3+ daily summaries | Yes (3) | Yes (3+) |
| Weekly Planning | Completed retro | Generate | Generate |

## Open Questions

1. Should rest days be default or opt-in for generation?
2. How much content do rest-day summaries need? (Minimal vs. full structure)
3. Should we support "any demo day" or document "recommended demo days"?
4. Do we need weekend summaries (Sat/Sun) or just weekday rest days?

## Success Criteria

- [ ] Can run morning routine demo on any weekday without "missing yesterday" error
- [ ] Weekly retro produces meaningful output with 3-5 days of data
- [ ] `regenerate_demo_dates.py --demo-day X` produces complete, valid data
- [ ] Demo script documents any day-of-week constraints

## Notes

**2025-12-11:** Feature created after discovering demo day alignment issues during presentation prep. Real personal workflow doesn't hit these gaps because daily logging is consistent. Synthetic data for demos needs more coverage or skills need more resilience (ideally both).
