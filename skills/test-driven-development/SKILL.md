---
name: test-driven-development
description: "Strict RED-GREEN-REFACTOR TDD cycle. Use during implementation. Write the failing test FIRST, then the minimum code to pass, then refactor. Never write production code without a failing test. Use when implementing features, fixing bugs, or when the user mentions TDD, testing, or test-first."
visibility: public
requires_body_cleanup: false
---
# Test-Driven Development

## The Cycle
1. **RED**: Write a failing test that describes the desired behavior
2. **GREEN**: Write the minimum code to make the test pass
3. **REFACTOR**: Clean up while keeping tests green

## Rules
- NEVER write production code before the test
- Each cycle should take < 5 minutes
- Run tests after every change
- If a test is hard to write, the design needs simplifying
