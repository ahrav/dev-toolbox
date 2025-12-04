---
description: Transform an ambiguous feature request into well-defined, actionable tasks
---

Decompose the following feature request into well-defined, actionable tasks:

**Request**: $ARGUMENTS

Follow the task-architect workflow:

1. **Parse & Score**: Analyze the request and calculate a complexity score (0-10) across 5 dimensions: Scope, Technical Unknowns, Approach Certainty, External Dependencies, and Cross-cutting Concerns. Output the score breakdown.

2. **Baseline Knowledge** (if score > 2): Use Glob and Grep to explore the codebase. Identify relevant files, existing patterns, and similar implementations.

3. **Domain Research** (if score > 5 OR external APIs involved): Invoke comprehensive-researcher for external docs, specs, and best practices.

4. **Solution Exploration** (if score >= 8 AND multiple approaches): Invoke multi-perspective-architect to compare 2-3 approaches. Present options to user if no clear winner.

5. **Task Definition**: Create atomic tasks grouped by theme. Each task needs:
   - Clear verb-first description
   - Files to modify (if known)
   - Success criteria
   - Dependencies (if any)

6. **Interactive Refinement**: Present tasks grouped by theme. User can accept, modify, add/remove tasks, or request more exploration. Loop until accepted.

7. **Write to todo.md**: On acceptance, add tasks to the appropriate workstream in tasks/todo.md.

Start by outputting your complexity score, then proceed through applicable phases.
