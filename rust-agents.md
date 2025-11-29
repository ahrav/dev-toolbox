# Repository Guidelines

## Session Workflow (Implementation Tasks Only)

**IMPORTANT**: A task is NOT complete until ALL three phases are finished:
1. ✅ Implementation Loop - code written and tests passing
2. ✅ Reviewer Loop - agents triggered and findings addressed
3. ✅ Ending a Session - todo.md updated and session documented

**If you stop after implementation without completing reviews and session close-out, the workflow is incomplete.**

Use this workflow when working on feature implementation, bug fixes, refactoring, or other code changes. Skip this workflow for questions, information requests, or exploratory discussions.

### Starting a Session
1. Read `tasks/todo.md` for current work items
2. Run `git status` to check for uncommitted work
3. Run `cargo check` to verify compilation
4. Select ONE task from todo.md to focus on

### Implementation Loop
For each task:
1. Read relevant source files first
2. Research and plan if complexity warrants it:
   - **Triggers**: Unfamiliar patterns, multiple valid approaches, performance-sensitive code, or external API/library usage
   - **Research**: Look up idiomatic patterns, best practices, official docs, RFCs, or relevant papers
   - **Approach comparison** (for significant choices):
     - List 2-3 candidate approaches with pros/cons
     - Score each on criteria: simplicity, performance, maintainability, idiomatic fit
     - Select the highest-scoring approach with rationale
   - **Document**: Add brief notes to todo.md alongside the task
3. Make smallest possible change
4. Write or update tests alongside the change when the code is testable; testing is part of implementation, not an afterthought
5. Run: `cargo build && cargo test && cargo clippy --all-targets --all-features`
6. Mark task complete in todo.md

---
✅ **Implementation Complete → Now proceed to Reviewer Loop below**

### Reviewer Loop
- Review the change as a black-box reviewer encountering the work fresh.
- Adjust depth to domain, complexity, and risk: idiomatic correctness, security, performance sensitivity, simplicity, design, and documentation as relevant.
- Capture findings and address them before ending the session when possible.

---
✅ **Reviews Complete → Now proceed to Ending a Session below**

### Ending a Session
1. Update `tasks/todo.md` - mark completed, add discovered items
2. Add Review entry with: what was done, decisions, issues, what's next
3. Ensure code compiles and tests pass

### Session Completion Checklist
Before finishing, verify you completed ALL steps:
- [ ] **Implementation**: Code written, tests passing, clippy clean
- [ ] **Reviews**: Appropriate agents triggered, findings addressed
- [ ] **Documentation**: `tasks/todo.md` updated with completed/new items
- [ ] **Session Notes**: Review entry added with decisions and next steps
- [ ] **Verification**: Final `cargo build && cargo test && cargo clippy` passes

**If any checkbox is incomplete, the session is not finished. Complete all steps before stopping.**

### Principles
- Make every change as simple as possible.
- Avoid massive or complex changes; keep the impact minimal.
- Check in with the user before beginning significant work.
- Provide high-level explanations of changes made.

