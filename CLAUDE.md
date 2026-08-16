
# Project's Working Practices — The Golden Rule

> - **The Golden Rule** governs *how* any work is approached at every stage — including, investigations, and non-pipeline tasks: understand before acting, plan before coding, record before closing.
> When a pipeline agent runs, it must still honor this discipline within its stage.

**Know before you act. Plan before you code. Record before you close.**

```
STEP 1 → UNDERSTAND (read existing code first)
STEP 2 → PLAN (phase-based, milestone-driven)
STEP 3 → EXECUTE (follow existing patterns)
STEP 4 → SNAPSHOT (record what changed)
```
Never skip or reorder steps.

## STEP 1 — UNDERSTAND (Knowledge First)
Before writing a single line of code or suggesting any solution:
1. **Read the relevant existing code** — files, modules, utilities, helpers, types, configs related to the work.
2. **Identify existing patterns** — naming, folder structure, state management, error handling, API/component patterns.
3. **Map what already exists** that could be reused, extended, or adapted.
4. **Only after** gaining context, think about the solution.

Mandatory output before planning: summary of code read · patterns identified · reuse-vs-new map.

## STEP 2 — PLAN (Phase-Based, Decoupled)
Never start coding without a written plan (What / Why / Phases with milestones). Each phase has a single concern; no phase depends on another phase's internal implementation — only on its output/contract. Present the plan and **wait for explicit approval before implementing**.

## STEP 3 — EXECUTE (Pattern-Consistent)
Follow the existing patterns from Step 1 strictly. Do not introduce new libraries/abstractions unless approved in the plan. Implement phase by phase; verify one before starting the next. Call out any deviation **before** making it.

## STEP 4 — SNAPSHOT (Local File Memory)
After completing any feature/issue/change, record a snapshot at
`.claude-snapshots/YYYY-MM-DD/[type]-[short-slug]/` with `before.md`, `after.md`, `summary.md`
(`[type]` = feature | issue | chore | refactor). Snapshots describe **behaviour and structure, not diffs**; one folder per work item; local files only (never Claude memory).

## INTERACTION RECORDS — `.claude-interactions/`
Preserve the *thinking/grooming/reasoning* behind decisions at
`.claude-interactions/YYYY-MM-DD/[topic-slug].md`. Write one when a discussion reaches a finalized decision/plan, when switching topics, and **always before `/compact`**. Record options considered *and rejected* with explicit reasoning. At the close of any decision-producing discussion, remind the user to save the record before compacting, and offer to write it.

## ANTI-PATTERNS (Never Do These)
Jumping into code before reading the codebase · proposing a solution with no written plan · mixing concerns across phases · starting Phase 2 before Phase 1 is verified · introducing new libraries/patterns without approval · skipping the snapshot because "it was small" · one giant snapshot for multiple unrelated changes.
