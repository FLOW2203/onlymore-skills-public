---
name: writing-plans
description: "Convert an approved design into an executable implementation plan. Use after brainstorming is complete and design is approved. Creates a sequence of 2-5 minute tasks with exact file paths, complete code, and verification steps."
visibility: public
requires_body_cleanup: false
---
# Writing Plans

Convert approved designs into granular implementation tasks.

## Task Format
Each task must specify:
- **File**: exact path to create/modify
- **Action**: create, modify, or delete
- **Code**: complete code (not pseudocode)
- **Verify**: how to confirm it works (test command or manual check)
- **Time**: estimated 2-5 minutes

## Rules
- Tasks must be independently executable
- Each task produces a verifiable result
- No task depends on unwritten code from a future task
- Save plan to docs/plans/
