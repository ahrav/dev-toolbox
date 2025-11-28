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
- Review the change as a black-box reviewer encountering the work fresh.
- Adjust depth to domain, complexity, and risk: idiomatic correctness, security, performance sensitivity, simplicity, design, and documentation as relevant.
- Capture findings and address them before ending the session when possible.

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

