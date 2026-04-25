---
name: systematic-debugging
description: "4-phase root cause analysis for bugs. Use when fixing bugs, investigating failures, or when something doesn't work as expected. Never guess — observe, hypothesize, test, fix."
visibility: public
requires_body_cleanup: false
---
# Systematic Debugging

## 4 Phases
1. **OBSERVE**: Reproduce the bug. Collect exact error messages, stack traces, logs.
2. **HYPOTHESIZE**: List 3+ possible causes ranked by likelihood.
3. **TEST**: For each hypothesis, design a minimal test to confirm or eliminate it. Start with most likely.
4. **FIX**: Fix the confirmed root cause. Verify the fix. Add a regression test.

## Rules
- Never apply a fix without confirming the root cause
- Always add a regression test
- Document what you found for future reference
