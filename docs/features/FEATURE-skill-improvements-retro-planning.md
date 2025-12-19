# F46: Skill Improvement - Retro & Planning Learnings

**Status:** Active - Implementation ready
**Effort:** Path B (1-2 hours to implement all improvements)
**Priority:** High (skill quality improvements for ongoing use)
**Source:** Session notes from Dec 7, 2025 monthly retro + planning; Week 8 retro (P2, P3)
**Created:** 2025-12-14

---

## Problem

During November monthly retro and December monthly planning, several skill gaps and improvement patterns were identified.

---

## P2 - Sunday Gap in Weekly Retros

**Source:** Week 8 retro

### Problem

Weekly retros don't explicitly load/review the prior Sunday's summary. Week boundaries should be Sunday-Saturday, not ambiguous.

### Why It Matters

- Sunday often has unique activity patterns (planning, rest, prep for week)
- Current skill asks for "this week's daily summaries" without specifying boundary
- Prior Sunday's summary has planning context relevant to the week
- Running retro on Sunday means that Sunday's morning activities get passively included but not explicitly loaded

### Fix Required in retrospective-base

1. Explicit week boundary definition: "Week = Sunday through Saturday"
2. Load sequence: "Load prior Sunday's summary FIRST (sets week context)"
3. Add checklist: "[ ] Prior Sunday summary loaded and reviewed"

### Example Guidance to Add

Add to retrospective-base, Section 2 "Load Context":

```markdown
**For weekly retros:**
- Week boundary: Sunday through Saturday
- Load PRIOR Sunday's summary first (this is when you planned the week)
- Then load Monday through Saturday summaries
- Total: 7 summaries (Sun-Sat) plus any planning docs

**Clarification:**
- Week N runs Sunday -> Saturday
- Retro happens on following Sunday
- Example: Week 9 retro on Sunday Dec 21 covers Sun Dec 15 -> Sat Dec 20
```

### Test Scenario

1. Run Week 9 retro on Sunday Dec 21
2. Should explicitly load and reference Sunday Dec 15's summary
3. Week 9 = Sun Dec 15 -> Sat Dec 20

---

## P3 - Scientific Method Framing

**Source:** Week 8 retro (enhanced from original F46 "n=1 science language discipline")

### Problem

Conversations tend toward premature conclusions. Language like "this works" or "this causes that" gets used when we only have 1-2 data points. Need more language of experimentation and exploration.

### Root Cause

Skills don't explicitly prompt for scientific method framing. Easy to slip into conclusory language when discussing observations.

### Desired Behavior

- Default to hypothesis/theory language over conclusion language
- Distinguish between: observations (what happened), hypotheses (proposed explanations), findings (patterns with multiple data points), conclusions (well-supported claims)
- Prompt for uncertainty calibration: "How confident? How many data points?"

### Terminology Table

| Term | Definition | Example |
|------|------------|---------|
| **Observation** | What actually happened (factual, single data point) | "Ran 20 minutes on Wed without stopping" |
| **Finding** | Pattern across multiple observations (3+ data points) | "3 of 3 runs this week completed without walk breaks" |
| **Hypothesis** | Proposed explanation, actively testing | "Banana 30 min before may prevent stomach issues" |
| **Experiment** | Structured test of hypothesis | "This week: banana exactly 30 min before each run" |
| **Conclusion** | Hypothesis validated with sufficient data | "After 3 weeks: 30-min pre-run banana = no stomach issues" |

### Language Guide

| Instead of... | Use... |
|---------------|--------|
| "This works" | "This showed promise in N instances" |
| "X causes Y" | "Hypothesis: X may contribute to Y" |
| "The pattern is..." | "Emerging pattern (N data points): ..." |
| "I've found that..." | "Current theory: ..." |
| "This is the solution" | "Experiment to try: ..." |

### Anti-Patterns to Avoid

- "I learned that X works" after 1 trial (premature conclusion)
- "X failed" after 1 trial (insufficient data)
- Treating correlation as causation

### Good Pattern

"Banana timing MAY be the factor (hypothesis). Testing this week (experiment). Will conclude after 3 successful trials (validation criteria)."

### Files to Update

- `skills/retrospective-base/SKILL.md` - Add "Language Discipline" section
- `skills/planning-base/SKILL.md` - Frame experiments properly
- `skills/daily-summary-base/SKILL.md` - "Insights" section uses proper terminology
- `skills/daily-morning-routine-base/SKILL.md` - Brief reminder about n=1 framing

### Example Section to Add

Add to retrospective-base (new section before "Core Principles"):

```markdown
## Scientific Language Discipline

**n=1 science requires precision:**

- **Observations:** What happened (single data point)
- **Findings:** Patterns across observations (multiple data points)
- **Hypotheses:** "Maybe X causes Y" (under active experiment)
- **Experiments:** Structured tests with clear success criteria
- **Conclusions:** Validated only after sufficient data (usually 2-3 weeks minimum)

**Anti-patterns to avoid:**
- "I learned that X works" after 1 trial (premature conclusion)
- "X failed" after 1 trial (insufficient data)
- Treating correlation as causation

**Good pattern:** "Banana timing MAY be the factor (hypothesis). Testing this week (experiment). Will conclude after 3 successful trials (validation criteria)."
```

---

## Trigger Pattern Issues

**Problem:** "monthly retro" and "december planning" didn't auto-trigger skills

**Fix:** Add to skill descriptions:
- `monthly retro/planning`
- `[month name] retro/planning`
- `retro then planning`

---

## Retrospective-base Improvements

| Pattern | Description |
|---------|-------------|
| Fractal time-scale review | Walk through smaller unit (week-by-week) before synthesis |
| Plan vs Actual section | Standard for monthly, optional for weekly |
| Per-section correction invitations | Pause after each major section for user correction |
| Meta-insights prompt | "What patterns emerged that weren't in the weekly retros?" |
| Balance check | Explicitly check for "What Didn't Work" asymmetry |

---

## Planning-base Improvements

| Pattern | Description |
|---------|-------------|
| Retro -> Planning flow | Suggest completing retro first if not done |
| User-driven theme identification | Reflect back priorities, let user name the theme |
| List -> Reflect -> Refine | User lists raw -> Claude organizes -> User confirms/adjusts |
| Natural phase breaks | For monthly, find natural halves based on deadlines/focus shifts |
| Check existing docs | Before generating, check if plan already exists for that period |
| Plans are scaffolding | Plans are removed after use; retros hold durable knowledge |
| Decision filter pattern | Every monthly plan produces 2-question filter to test activities |

---

## Open Questions (Deferred)

- Should monthly-retrospective/planning be separate skills or modes of base skills?
- Gratitude section: include or skip for monthly retros?
- How detailed should weekly outline be in monthly plan?

---

## Implementation Order

1. Trigger pattern fixes (quick win - frontmatter only)
2. P2 Sunday gap (retrospective-base "Load Context" section)
3. P3 Scientific method (add section to all 4 skills)
4. Remaining methodology improvements

---

## Success Criteria

- [ ] Trigger patterns added to skill descriptions
- [ ] Week boundary explicitly defined as Sunday-Saturday
- [ ] Prior Sunday loaded first in weekly retro flow
- [ ] Scientific language section added to retrospective-base
- [ ] Experiments framing improved in planning-base
- [ ] Insights section guidance updated in daily-summary-base
