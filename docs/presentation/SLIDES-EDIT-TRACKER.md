# Slides Edit Tracker

Working document for Dec 12, 2025 presentation.

---

# Current Status

## Pre-Presentation TODO
- [x] Save screenshot to `screenshots/project-docs.png`
- [ ] Dry run to test timing
- [ ] Decide: keep both story slides or pick one?

## Screenshots Needed (for standalone deck)
- [x] `project-docs.png` - Project sidebar with documents
- [ ] `rob-setup.png` - Project setup skill output
- [ ] `rob-morning.png` - Morning routine "gm" output
- [ ] `rob-daily-summary.png` - Completed daily summary artifact
- [ ] `rob-weekly-retro.png` - Weekly retrospective output
- [ ] `rob-weekly-plan.png` - Weekly plan with L0-L3 levels

## Optional Refinements (if time permits)
- [ ] "The Pitch" - refine tone for AI engineers
- [ ] Appendix slides - review/rework

---

# Completed Work

## Narrative Reorder (Dec 11)
Moved Evolution section to early in presentation:
```
Hook → Evolution → Platform → Skills → Demo → Architecture → Lessons → What's Next
```

## Section Dividers Added
- "Evolution" → after "What if you could..."
- "The Platform" → before Projects: Mental Model
- "Skills" → before What's a Skill?
- "Demo" → before Demo Time: Rob
- "Architecture" → before Repo Structure
- "Lessons" → before What I Learned
- "What's Next" → before Where This Is Going

## Slides Added
- Demo 0: Project Setup
- LLMs Are Bad at Dates
- Skills Are Global (Pain Point)
- Onboarding Experiments
- Safety Boundaries
- The Dev Process
- The Bitter Lesson

## Key Edits
- Title uses YAML subtitle (removed duplicate slide)
- "Conversation" → "Permanent chat, context not retained"
- The System slide: annotated gm as conversation, rest as artifacts
- Fractal Compression: two clear graphs (daily→weekly, weekly→monthly)
- .zip/.skill: clarified skill-creator outputs .skill, uploader needs .zip
- Global CSS for smaller fonts (no more overflow)

---

# Slide Ideas (Not Added - Future/Optional)

## "Claude Code for Markdown, Not Python"
Used Claude Code to generate markdown, minimal Python. The "code" was mostly prompts.

## "Project Management in Markdown"
Feature queue tracked in markdown. Git tracks changes. Scales to n=1.

## "Microagent Teaser"
Same patterns, any model. Tool-calling models (Llama, Qwen). Not locked to Claude.

---

# Notes

Re-render command:
```bash
pandoc docs/presentation/SLIDES-dec-12.md -t revealjs -s -o docs/presentation/slides.html -V theme=white -V transition=slide
```

Speaker notes use `::: notes` blocks.
