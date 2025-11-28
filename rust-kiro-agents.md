# Repository Guidelines

## Session Workflow (Implementation Tasks Only)

Use this workflow when working on feature implementation, bug fixes, refactoring, or other code changes. Skip this workflow for questions, information requests, or exploratory discussions.

### Starting a Session
- Read `tasks/todo.md` for current work items.
- Run `git status` to check for uncommitted work.
- Run `cargo check` to verify compilation.
- Select ONE task from todo.md to focus on.

### Implementation Loop
- Read relevant source files first.
- Research and plan if complexity warrants it:
  - **Triggers**: Unfamiliar patterns, multiple valid approaches, performance-sensitive code, or external API/library usage.
  - **Research**: Look up idiomatic patterns, best practices, official docs, RFCs, or relevant papers.
  - **Approach comparison** (for significant choices):
    - List 2-3 candidate approaches with pros/cons.
    - Score each on criteria: simplicity, performance, maintainability, idiomatic fit.
    - Select the highest-scoring approach with rationale.
  - **Document**: Add brief notes to todo.md alongside the task.
- Make the smallest possible change.
- Write or update tests alongside the change when the code is testable; testing is part of implementation, not an afterthought.
- Run: `cargo build && cargo test && cargo clippy --all-targets --all-features`.
- Commit with a descriptive message.
- Mark the task complete in `tasks/todo.md`.

### Reviewer Loop
After completing implementation, trigger reviews using background Task agents to ensure fresh context.

**Step 1: Analyze Changes**
Before selecting reviewers, assess the implementation:
- **Volume**: How many files/lines changed? (small: <50 lines, medium: 50-200, large: 200+)
- **Complexity**: Simple CRUD, algorithmic logic, concurrency, state management?
- **Sensitivity**: Performance-critical paths? Security-sensitive code? Public API surface?
- **Scope**: Isolated change or cross-cutting across modules?

**Step 2: Select Reviewers Based on Analysis**
Use the change analysis to determine which agents and how many:

| Change Characteristics | Recommended Agents |
|------------------------|-------------------|
| Small, isolated, simple | `code-reviewer` only |
| Language-specific patterns | Add language expert (`rust-expert`, `python-expert`, `golang-expert`) |
| Auth, input validation, crypto | Add `security-auditor` |
| Hot paths, data structures, I/O | Add `performance-engineer` |
| New modules, API changes, cross-cutting | Add `architect-review` |
| Large or complex changes | Multiple agents in parallel |

**Step 3: Launch Reviews**
For each selected agent, provide:
- Files changed with paths
- Summary of what was implemented and why
- The change analysis (volume, complexity, sensitivity)
- Specific focus areas relevant to that agent's expertise

**Step 4: Address Findings**
Collect agent findings and address them before ending the session when possible.

### Ending a Session
- Update `tasks/todo.md`: mark completed items and add anything discovered.
- Add a Review entry noting what was done, decisions, issues, and what's next.
- Ensure code compiles and tests pass.
- Commit any uncommitted work.

### Principles
- Make every change as simple as possible.
- Avoid massive or complex changes; keep the impact minimal.
- Check in with the user before beginning significant work.
- Provide high-level explanations of changes made.

