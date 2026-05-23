# Project Log: Writing the Project Management Guide

*A meta tracking doc for the guide itself. Update this as work progresses to avoid context drift across sessions.*

---

## Project Summary

**Deliverable:** *Project Management Made Simple: A Beginner's Guide to Getting Things Done* — a written guide plus a matching template pack (Excel, Word, and possibly Notion).

**Audience:** Beginners to intermediates. Should feel engaging and approachable, not academic. Usable as a refresher for people who already know some of this but want a clean mental model and reusable tools.

**Tone:** Warm, plain, practical. Short sentences. Analogies welcome. Jargon only when defined. Assume the reader is smart but busy.

**Running example:** A community cleanup event threaded through every chapter. Eventually paired with a worked end-to-end appendix that shows every template filled in for that project.

---

## File Inventory

Everything lives in this folder. Two parallel representations are kept in sync:

- **Split chapter files** (the single source of truth; edit these):
  - `00_front_matter.md`
  - `01_introduction.md`
  - `02_quick_start.md`
  - `02a_choosing_your_approach.md`
  - `03_chapter_1_define_goals_scope.md`
  - `04_chapter_2_tasks_prioritization_tools.md`
  - `05_chapter_3_planning_timelines_monitoring_changes.md`
  - `06_chapter_4_communication_leadership.md`
  - `07_chapter_5_troubleshooting.md`
  - `08_chapter_6_closing_reflecting.md`
  - `09_appendices.md`
  - `09a_worked_example.md`
  - `10_conclusion.md`

- **Compiled single-file version (derived):** `project_management_guide_v5_compiled.md`

- **Original rough draft (reference only):** `original_project manangement.md`

**Build rule:** the split files are the only editable surface. The compiled v5 is **generated from the splits** by concatenating them in order and joining with `\n---\n\n` as the section separator. Never edit the compiled file by hand — rebuild it instead. This eliminates the double-edit / drift problem.

**Rebuild command (Python):**
```python
files = ["00_front_matter.md", "01_introduction.md", "02_quick_start.md",
         "02a_choosing_your_approach.md", "03_chapter_1_define_goals_scope.md",
         "04_chapter_2_tasks_prioritization_tools.md",
         "05_chapter_3_planning_timelines_monitoring_changes.md",
         "06_chapter_4_communication_leadership.md",
         "07_chapter_5_troubleshooting.md",
         "08_chapter_6_closing_reflecting.md",
         "09_appendices.md", "09a_worked_example.md", "10_conclusion.md"]
parts = [open(f, encoding="utf-8").read().rstrip() + "\n" for f in files]
open("project_management_guide_v5_compiled.md", "w", encoding="utf-8").write("\n---\n\n".join(parts))
```

Run this at the end of any session where split files were edited.

---

## Style Conventions (preserve these)

- **Voice:** Second person, conversational, occasional dry humor is fine.
- **Structure:** Short paragraphs. Bulleted lists only when they earn it. No deep nesting.
- **Chapter pattern:**
  1. Short opener paragraph
  2. "Running Example" callout tying to the cleanup project
  3. Concept explanation with at least one "Why this matters" line
  4. Steps or sub-topics
  5. One worked example or table
  6. Quick tips
  7. Practical exercise (where applicable)
  8. Chapter checklist
  9. *(new, to add)* Reflection prompts
  10. *(new, to add)* Cheat-sheet summary
- **Analogies:** Use them sparingly but deliberately. Existing ones to preserve: *packing for a trip* (Ch 2 opener), *dominoes* (critical path), *GPS/address* (SMART goals), *weather forecast* (risk matrix).
- **Encouragement lines:** The "If you feel unsure…" / "Keep it simple…" reassurance lines work but can get formulaic. Use them where they help, not as a tic.
- **Don't say:** "genuinely," "honestly," "straightforward." Avoid em-dash-heavy prose unless it's doing real work.

---

## Completed Milestones

- **v5 compiled from split files** (prior session, by codex). Six chapters, front matter, appendices, glossary, acronyms, conclusion, running example.
- **Table of Contents populated** in both front matter and compiled v5 (was an empty header).
- **Tools Overview deepened** (Ch 2). Trello, Asana, Kanban, Microsoft Planner, Google Workspace, Paper — each now has What / Key features / Best for / How to use blocks.
- **Critical Path example fleshed out** (Ch 2). Explicit dependencies, path trace, float explained, domino analogy added.
- **Analogies added:** GPS/address for SMART goals (Ch 1), weather forecast for risk matrix (Ch 5), dominoes for critical path (Ch 2), packing-for-a-trip for WBS (Ch 2 opener).
- **Methodology orientation added** as new section `02a_choosing_your_approach.md` (Waterfall / Agile / Hybrid + Agile basics glossary).
- **Kickoff & Charter subsection** added to the top of Chapter 1 (stakeholder interviews, 7-item kickoff agenda, one-page charter template, cleanup example).
- **Estimation techniques expanded** (Ch 3): three-point, t-shirt sizing, analogous, planning poker + rules of thumb.
- **Status reporting deepened** (Ch 4): RAG status, update structure, blocker framing, decisions-needed framing, weak-vs-strong update examples.
- **ASCII visuals added**: WBS tree (Ch 2), critical path network (Ch 2), Kanban board (Ch 2), Gantt strip (Ch 3), risk matrix quadrant (Ch 5).
- **Remote/hybrid callouts** added as blockquote tips in Chapters 1, 2, 4.
- **Reflection prompts** added to every chapter (3 questions each).
- **Worked end-to-end cleanup example** added as `09a_worked_example.md` — 12 filled-in templates from charter through lessons learned.
- **Per-chapter cheat sheets** added at the end of every chapter (Big ideas / Do this / Avoid this / Try it).
- **Build process switched to split-only editing + rebuild.** Compiled v5 is now generated from the splits, eliminating the double-edit drift risk.
- **Gemini round 1 feedback incorporated:**
  - **Meeting Decision Checklist** (Ch 4) — five-question filter to decide meeting vs. message.
  - **Bias Factor pro tip** (Ch 3) — expanded into a callout with a concrete tracking table (Estimated / Actual / Ratio).
  - **Paper-as-V1 reframe** (Ch 2) — paper now leads the Tools Overview with explicit "start here, graduate to software when X happens" framing.
- **Diff verification:** after rebuild, split concatenation vs. compiled v5 differ only by the 12 `\n---\n\n` separators. Clean.
- **Polish pass (round 1):** removed all 59 em dashes across the guide, rewrote sentences rather than just swapping punctuation. Removed AI tells (no "genuinely," "honestly," "delve," "leverage," "streamline," "moreover," etc.). Tightened chapter openers in 1, 2, 3, 4, 5, 6. Warmer voice in Intro, Quick Start, and Conclusion. TOC chapter titles now use plain hyphens to match the actual chapter headers. Rebuilt compiled v5. Compiled file: 0 em dashes, 2024 lines.

---

## Backlog (prioritized)

### High-leverage text additions
1. **Methodology orientation + Agile basics.** New section "Choosing Your Approach: Waterfall, Agile, Hybrid" between Quick Start and Chapter 1, including a short Agile/Scrum primer (sprints, standups, backlogs, retros, MVP).
2. **Kickoff & Charter.** New subsection at the top of Chapter 1 covering stakeholder interviews, kickoff meeting, and a one-page project charter.
3. **Worked end-to-end example.** New appendix showing every template filled in for the community cleanup project, from charter to lessons learned. Doubles as a reference for the template pack.

### Medium-leverage text additions
4. **Simple ASCII visuals** in Chapters 2, 3, and 5: WBS tree, Kanban board, critical path network, Gantt strip, risk matrix quadrant.
5. **Per-chapter cheat sheets** — printable summary cards at the end of each chapter.
6. **Estimation techniques expansion** in Chapter 3: T-shirt sizing, analogous estimation, planning poker alongside the existing three-point reference.
7. **Status reporting depth** in Chapter 4: RAG status, blocker framing, decisions-needed callouts, good vs. bad update examples.

### Nice-to-have
8. **Remote/hybrid callouts** where they matter (meetings, monitoring, collaboration).
9. **Reflection prompts** at the end of each chapter (3 questions).
10. **Second running example** (product launch or process improvement) — optional, may be covered by the worked-example appendix.

### Template / printable pack (phase 2, after text is locked)
- Excel: task tracker, RACI, budget snapshot, risk matrix + grid, change log, status dashboard, simple timeline, stakeholder map.
- Word: one-page project plan, meeting agenda, weekly status update, lessons learned, change request impact review, WBS outline.
- Notion: task tracker, stakeholder map, risk log, change log (database-style).
- Possibly: printable cheat-sheet PDF per chapter.

---

## Decisions Made

- **File structure:** keep the numbered split files. New content gets `NNa_` suffixes to preserve ordering without renumbering everything downstream.
- **Compiled v5 is the read-through artifact.** The split files are the editing surface.
- **Running example is the cleanup event**, at least for the first worked-through pass. A second example is parked unless it's needed.
- **Templates come after the text is locked.** We don't want to rebuild printables if the text shifts.
- **Printables and xlsx templates are deferred** until we finish the text additions.

---

## Parking Lot (ideas to consider, not committed)

- Glossary entries for new terms (sprint, standup, backlog, retro, MVP, charter, kickoff) once the methodology section lands.
- A second running example (product launch or internal process) threaded through the guide.
- A one-page "Quick Reference Card" pulling the five essential steps, key definitions, and the checklists into a printable single sheet.
- Light use of callout formatting (e.g., `> Remote-friendly tip:`) to make scannable boxes without fancy rendering.
- A short "When a project is the wrong answer" sidebar (not every initiative needs a PM framework).

---

## Next Up

All Phase 1 text additions (items 1–10) are complete. The manuscript is stable and ready for review.

Phase 2 (pending user go-ahead): the template and printable pack.

- Excel templates: task tracker, RACI, budget snapshot, risk matrix, change log, status dashboard, timeline, stakeholder map.
- Word templates: one-page project plan, meeting agenda, weekly status update, lessons learned, change request, WBS outline.
- Optional Notion database templates.
- Optional printable cheat-sheet PDF per chapter.

---

*Last updated: 2026-04-18.*
