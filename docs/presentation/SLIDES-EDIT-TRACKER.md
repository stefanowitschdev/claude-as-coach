# Slides Edit Tracker

Working document for slide-by-slide review. Using titles as anchors since slide numbers will shift.

**Status:** 🔴 Needs work | 🟡 Minor tweaks | 🟢 Good

---

## TITLE: "Claude-as-Coach"
**Status:** 🔴 Merge with next slide

**Current:**
```
# Claude-as-Coach
**Zero-build context management for behavior change**
Zach Morek | Dec 12, 2025
```

**Issue:** Duplicated with "The Problem" slide

**Action:** Merge into single opener or make title minimal

---

## TITLE: "The Problem"
**Status:** 🔴 Merge with title slide

**Current:**
```
- Context dies between Claude conversations
- Building agents is overkill for personal tracking
- You want **continuity**, not infrastructure
```

**Issue:** Duplicates title slide framing

**Action:** Delete after merging content into title slide

---

## TITLE: "What if you could just... talk to it?"
**Status:** 🟡 Needs tuning

**Feedback:** Problem statement needs tuning

**Action:** Refine the hook - make it land better for AI engineers

---

## TITLE: "Claude.ai Projects"
**Status:** 🟡 Good idea, not landing

**Feedback:** Like the concept but not sure it's landing right

**Action:** Rework to be clearer about why Projects specifically (vs building agent, vs Claude Code)

---

## TITLE: "Projects: The Mental Model"
**Status:** 🟢 Great

**Feedback:** Great summary of why claude.ai projects as exploration space over building an agent or fitting into Claude Code (which may have system prompts tuned for coding, not journaling)

**Action:** Keep, possibly expand on this reasoning

---

## TITLE: "What's a Skill?"
**Status:** 🔴 Formatting + content

**Feedback:**
- Formatting issue with visual
- Better served showing Rob's scenario 4
- Need to explain: Skills have name + description. Description explains when to load full skill into context
- Analogy: "A skill is a kind of function that can run on an LLM"

**Action:**
- Fix formatting
- Add name/description explanation
- Consider showing Rob scenario 4 visual instead

---

## TITLE: "Skills: Just Markdown"
**Status:** 🟢 Good

**Action:** Keep as is

---

## TITLE: "The .zip/.skill Confusion"
**Status:** 🟡 Needs accuracy

**Feedback:** Not totally accurate - need to clarify and link to exact documents/screenshots showing dissonance

**Action:**
- Verify accuracy
- Add links to Anthropic docs showing the issue
- Consider adding screenshot

---

## TITLE: "Projects vs Claude Code"
**Status:** 🟡 Good start, needs expansion

**Feedback:**
- Should specify that claude.ai conversation agent can create artifacts that download or add to project documents
- Good start at explaining why this approach was chosen

**Action:** Add artifact → project document flow explanation

---

## TITLE: "The System: Daily → Weekly Loop"
**Status:** 🔴 Needs differentiation

**Feedback:**
- Need to differentiate conversations vs artifacts (that become project documents)
- Possibly add slide showing expansion to different time scales
- "Summary of summaries" concept
- "Schrodinger's RAG - dead or alive depending on when you open the repo"

**Action:**
- Split into multiple slides?
- Add time scale expansion visual
- Clarify conversation vs artifact vs document

---

## TITLE: "Fractal Compression"
**Status:** 🟡 Experimental, needs nuance

**Feedback:**
- Monthly interval may compress too frequently in practice
- "Nothing lost" is inaccurate
- Curation process follows SWE sprint retro: What worked (more) / What didn't (experiment) / Retro-retro
- Curates context, simplifies architecture dramatically
- Requires manual curation

**Action:**
- Soften "nothing lost" claim
- Add nuance about manual curation
- Mention sprint retro pattern

---

## TITLE: "Demo Time: Rob the Runner"
**Status:** 🟢 Great start

**Action:** Will iterate on demos 13-21

---

## TITLES: Demo slides (1-4) + outputs
**Status:** 🟢 Great start

**Action:** Iterate as needed

---

## TITLE: "Base + Personal Skill Pattern"
**Status:** 🟡 Terminology fix

**Feedback:** "merges" is inaccurate - Claude combines skills at runtime (demonstrated in Alice examples)

**Action:** Change "merges" to "combines at runtime" or similar

---

## TITLE: "The Evolution"
**Status:** 🔴 Major rework - split into multiple slides

**Feedback:** Timeframes inaccurate. Real progression was:

**v1:** Giant Google Doc with daily logging
- Gaining insights was challenging
- Required manual effort or building systems
- Wanted single place for: project work, exercise, sleep, diet
- Too much cognitive load sifting through it

**v2:** Various journaling agent attempts
- General agent conversations
- Create summary → copy/paste into new chat daily

**v3:** Projects + saving to documents
- Instructions saved as documents
- Didn't realize project docs always in context
- Wasted tokens reading files already in context
- Burned tokens on instruction docs always loaded

**v4:** Pushed instruction docs to skills
- Skills only loaded as needed
- Retro instructions not included every day

**v5:** Skill inheritance experiments
- Personal process → shareable framework
- Structural vs personal specific
- General goal vs my specific goal
- claude-as-coach-combined = claude-as-coach + claude-as-coach-personal

**Action:**
- Split into multiple slides showing this progression
- Visualize context waste problem (like `/context` command)
- Show the "aha moments" at each transition

---

## TITLE: "What I Learned"
**Status:** 🟡 Add "bitter lesson" angle

**Feedback:**
- Why over-engineer when context windows have grown?
- Easy to summary-of-summary and keep docs in context
- Lower friction than RAG
- Agent has memory system that decays over time, like a person

**Action:** Add the "bitter lesson" framing - simpler beats complex

---

## TITLE: "Platform Limitations (Real Talk)"
**Status:** 🟢 Useful, tune later

**Action:** Keep, refine as needed

---

## TITLE: "Where This Is Going"
**Status:** 🔴 Formatting needs work

**Action:** Fix formatting

---

## TITLE: "Try It Yourself"
**Status:** 🟡 Reprioritize

**Feedback:** Prioritize bootstrap process, deprecate manual quickstart

**Action:**
- Focus on bootstrap flow
- Make it simpler/clearer

---

## TITLE: "The Pitch"
**Status:** 🟡 Tone needs work

**Feedback:** Like showing low/zero build with simple primitives, but tone needs adjustment

**Action:** Refine tone for AI engineer audience

---

## TITLE: "Questions?"
**Status:** 🔴 Too sparse

**Feedback:** Rather than just "questions", show information-rich summary of all basic concepts

**Action:** Replace with summary slide that can hold during Q&A

---

## TITLES: Appendix slides
**Status:** 🔴 Needs work

**Action:** Rework appendix content

---

# Edit Queue

Priority order for edits:

1. [x] Merge title + problem slides
2. [x] Split "Evolution" into multiple slides (big one)
3. [x] Fix "What's a Skill?" formatting + content
4. [x] Add conversation vs artifact vs document differentiation
5. [x] Fix "Base + Personal" terminology ("combines" not "merges")
6. [x] Replace "Questions?" with summary slide
7. [x] Add bootstrap focus to "Try It Yourself"
8. [x] Tune remaining slides (Pass 2)
9. [x] Fix formatting issues throughout (global CSS)

---

# Pass 2 Feedback (Dec 11 review) - COMPLETED

## Structural Issues - ✅ ALL DONE

### Slides 1-2: Title + Problem ✅
**Resolution:** Merged into single title slide with tagline "Context management without heavy infrastructure"

### Slides 2-3: Personal Story ✅
**Resolution:** Added BOTH options as separate slides:
- "My Journey" (Google Docs → conversation → project → skills)
- "The Goal" (atomic habits story)
Can pick one or keep both during dry run.

### Slide 4: "What if you could..." ✅
**Resolution:** Refined to "flexible system" angle with "No agents to build. No RAG to configure."

### Slide 5: "Claude.ai Projects" ✅
**Resolution:** CUT - content covered elsewhere. Speaker notes moved to Mental Model.

### Slide 6: "Projects: Mental Model" ✅
**Resolution:** Replaced ASCII with screenshot reference.
**TODO:** Save screenshot to `screenshots/project-docs.png`

### NEW: "Project Primitives" ✅
**Added:** New slide explaining primitives (Conversation, Artifact, File, Memory, Instructions)

## Narrative Flow Issues - ✅ ALL DONE

### Reorder: Primitives → Loop → Skills ✅
**Resolution:** Moved loop slides (System, Conversations→Artifacts, Fractal) to follow Primitives, before Skills explanation.

### ".zip/.skill Confusion" ✅
**Resolution:** Added Anthropic doc links as speaker notes for reference during talk.

### "Projects vs Claude Code" ✅
**Resolution:** Fixed with global CSS (smaller default font).

### "Conversations → Artifacts → Documents" ✅
**Resolution:** Fixed with global CSS.

### "Fractal Compression" ✅
**Resolution:** Changed "Nothing lost" → "Manual curation. What worked → keep. What didn't → learn."

## Demo Section - ✅ ALL DONE

### Rob scenarios intro ✅
**Resolution:** Improved storytelling: "Who/Where/Today" format, sets scene for Sunday morning planning.

### "L0-L3 Success Framework" ✅
**Resolution:** Added "This framework emerged over time. Works for me - YMMV."

## Later Slides - ✅ ALL DONE

### "Repo Structure" ✅
**Resolution:** Updated to show claude-as-coach-combined with public/private split.

### "Try It Yourself" ✅
**Resolution:** Updated with project-coach-setup skill, reference to experiments/.

## Global Formatting - ✅ DONE

**Resolution:** Added global CSS in YAML front matter:
- Base font: 28px
- Code blocks: 0.7em
- Tables: 0.8em
- No more overflow issues

---

# Still Open

## Pre-Presentation TODO
- [x] Save screenshot to `screenshots/project-docs.png`
- [ ] Dry run to test timing
- [ ] Decide: keep both story slides or pick one?

## Screenshots Needed (for standalone deck)
- [x] `project-docs.png` - Project sidebar with documents
- [ ] `rob-morning.png` - Morning routine "gm" output
- [ ] `rob-daily-summary.png` - Completed daily summary artifact
- [ ] `rob-weekly-retro.png` - Weekly retrospective output
- [ ] `rob-weekly-plan.png` - Weekly plan with L0-L3 levels

## Section Title Slides - ✅ DONE

Added section dividers between major presentation sections:
- "The Platform" → before Projects: Mental Model
- "Skills" → before What's a Skill?
- "Demo" → before Demo Time: Rob
- "Architecture" → before Repo Structure
- "Evolution" → before Evolution v1-v2
- "Lessons" → before What I Learned
- "What's Next" → before Where This Is Going

## Optional Refinements (if time permits)
- [ ] "The Pitch" - refine tone for AI engineers
- [ ] "What I Learned" - add "bitter lesson" angle
- [ ] Appendix slides - review/rework

## New Slides to Consider Adding
See "New Slides to Add" section below - these are optional based on timing.

---

# New Slides to Add

## TITLE: "The Dev Process" (clarify "zero build")

**Concept:** Not exactly "zero build" - iterated on how to use existing primitives

**Primitives explored:**
- Conversation
- Artifact
- Project document
- Memories (opted to stop actively managing)
- Base project instructions (less useful than documents - harder to track in git)

**Key insight:** Project docs are easier to track in claude-as-coach-personal git repo than base instructions

---

## TITLE: "Claude Code for Markdown, Not Python"

**Concept:** Used Claude Code to generate a LOT of markdown, minimal Python

**Python written:**
- Unpack skills for easier git tracking
- Handle `.skill` / `.zip` compatibility
- Generate synthetic data templates with correct dates (date-specific summaries/retros)

**Key insight:** The "code" I wrote was mostly prompts and markdown instructions

---

## TITLE: "LLMs Are Bad at Dates"

**Concept:** Critical lesson - LLMs make up dates that don't exist

**Solution:** Must use tool calls to give ground truth

```bash
TZ='America/New_York' date '+%A, %B %d, %Y'
```

Every skill that deals with dates starts with this. No assumptions.

---

## TITLE: "Project Management in Markdown"

**Concept:** Feature queue tracked in markdown - Claude Code friendly minimalist PM

**Show:** FEATURES.md structure or similar

**Why it works:**
- Claude Code can read/update it
- Git tracks changes
- No external tooling needed
- Scales down to n=1

---

## TITLE: "Microagent Teaser"

**Status:** Closed source for now, open source soon

**Concepts to tease:**
- Same patterns, any model
- Subagents for code quality
- Tool-calling models (Llama, Qwen, etc.)
- Not locked to Claude

**Note:** If we make enough progress on slides today, can clean up repo and share early draft openly

---

## TITLE: "Subagents for Code Quality"

**Concept:** More relevant for microagent discussion

**Pattern:** Specialized subagents for specific tasks

**Defer to:** Microagent deep-dive (future session)

---

## TITLE: "Skills Are Global (Pain Point)"

**Concept:** Platform limitation - skills not project-scoped

**The problem:**
- My account is both prod AND dev for skills
- Have to manually toggle/remove skills to test changes
- No way to have "dev skill" vs "prod skill" per project

**Workaround:**
- Naming convention: `production-*` vs `development-*`
- Manual toggling in Settings > Capabilities

**Hope:** Anthropic adds project-scoped skills in future
(Or hire me to build it lol)

---

## TITLE: "Experiments & Feature Tracking"

**Concept:** Show how experimentation and feature tracking works

**Show:**
- `docs/experiments/` - onboarding approaches, etc.
- `docs/FEATURES.md` - feature queue structure

**Why it matters:**
- Low-friction experimentation
- Git-tracked decision history
- Claude Code can help maintain it

---

# Notes

- Re-render after significant changes: `pandoc docs/presentation/SLIDES-dec-12.md -t revealjs -s -o docs/presentation/slides.html -V theme=white -V transition=slide`
- Speaker notes use `::: notes` blocks
- Test at 4pm today

## Strategy

**Build comprehensive first** → test run → triage lower priority slides to appendix

Don't pre-optimize. Get all the content in, then cut based on actual timing.

## Meta: Presentation as Documentation

This presentation doubles as a **project review**:
- Summarize features discussed across sessions
- Show roadmap (what's done, what's next)
- Document decisions along the way
- Clean up toward **1.0.0 release**

The slides become living documentation of the project's evolution and direction.
