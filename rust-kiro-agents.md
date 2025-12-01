# Repository Guidelines

## Session Workflow (Implementation Tasks Only)

**IMPORTANT**: A task is NOT complete until ALL four workflow loops are finished:
1. ✅ Scoping Loop - task validated and ready for implementation
2. ✅ Implementation Loop - code written and tests passing
3. ✅ Reviewer Loop - agents triggered and findings addressed
4. ✅ Session Close - todo.md updated and session documented

**If you stop after implementation without completing reviews and session close-out, the workflow is incomplete.**

Use this workflow when working on feature implementation, bug fixes, refactoring, or other code changes. Skip this workflow for questions, information requests, or exploratory discussions.

---

## Task Management Structure

Use workstreams (not phases) to group tasks; numbering is only for traceability so efforts can run in parallel and archive independently.

### Directory Layout
```
tasks/
├── todo.md              # Active work only (index to other files)
├── backlog.md           # Future work, unprioritized ideas
└── archive/
    ├── YYYY-MM-name.md  # Completed workstreams with review notes
    └── ...
```

### File Responsibilities

**todo.md** - Active work only
- Current workstream tasks (5-10 max)
- Blocked items requiring resolution
- Index links to archive and backlog
- Review entries for current workstream (5-10 max)

**backlog.md** - Future work
- Upcoming workstreams and their tasks
- Ideas and enhancements not yet scheduled
- Technical debt items discovered during work

**archive/YYYY-MM-name.md** - Historical record
- Completed tasks from that workstream
- All review entries from sessions in that workstream
- Design decisions and their rationale

### Archival Rules

**Trigger**: Archive when a workstream completes (all tasks marked done)

**Process**:
1. Create `archive/YYYY-MM-name.md` with workstream name and date range
2. Move all completed tasks from todo.md to archive file
3. Move all review entries for that workstream to archive file
4. Update todo.md index to reference new archive
5. Promote next workstream from backlog.md to todo.md (if ready)

**todo.md size limit**: If active tasks exceed 10 or Review section exceeds 10 entries, archival is overdue.

---

## Starting a Session

### Steps
1. Read `tasks/todo.md` for current work
2. Check for uncommitted work (`git status` or equivalent)
3. Verify project builds/compiles (`cargo check`)
4. Select ONE task from todo.md to focus on

### Exit → Enter Scoping Loop
Conditions met:
- [ ] todo.md read and task selected
- [ ] No uncommitted work blocking progress
- [ ] Project builds successfully

---

## Scoping Loop

**Purpose**: Validate task is ready before writing code. Effort scales with ambiguity.

### Step 1: Read Task Context
- Read the task description in todo.md
- Identify referenced files, modules, or prior tasks
- Check if task references external specs (RFCs, docs, APIs)

### Step 2: Assess Readiness
Score the task on these dimensions:

| Dimension | Ready (0) | Needs Work (1) | Blocked (2) |
|-----------|-----------|----------------|-------------|
| **Scope** | Single, atomic change | Multiple concerns mixed | Unclear boundaries |
| **Context** | All files identified | Some files unknown | Major unknowns |
| **Approach** | Obvious implementation | 2-3 viable approaches | No clear path |
| **Dependencies** | None or resolved | Soft dependencies | Hard blockers |

**Score interpretation**:
- **0-2**: Task is ready → proceed to implementation
- **3-5**: Clarification needed → execute Step 3
- **6+**: Task blocked → decompose or escalate to user

### Step 3: Clarification Actions (if score 3+)

| Gap Type | Action |
|----------|--------|
| Scope unclear | Split into subtasks, update todo.md |
| Missing context | Read referenced files, add notes to task |
| Multiple approaches | Enter Research Step (Step 4) |
| External API/spec | Fetch docs, summarize key constraints in todo.md |
| User intent unclear | **STOP** - Ask user before proceeding |

### Step 4: Research Step (if triggered)
For tasks requiring design decisions:
1. Identify the specific question (e.g., "streaming vs buffered?")
2. Research: check docs, prior art, RFCs, existing codebase patterns
3. Compare 2-3 approaches with pros/cons
4. Document findings in todo.md under the task
5. Select approach with brief rationale

### Step 5: Confirm Ready
Before exiting, verify:
- [ ] Task scope is single, atomic change
- [ ] All source files identified
- [ ] Approach selected (if multiple existed)
- [ ] No blocking dependencies

### Exit → Enter Implementation Loop
**Trigger**: All Step 5 checkboxes satisfied

### Exit → Stop and Ask User
**Trigger**: Score 6+ OR "User intent unclear" gap identified

---

## Implementation Loop

### Steps
1. Read relevant source files first
2. Make smallest possible change
3. Write or update tests alongside the change
4. Run build, test, and lint commands: `cargo build && cargo test && cargo clippy --all-targets --all-features`
5. If tests fail, iterate until green
6. Mark task complete in todo.md

### Research During Implementation
If complexity emerges during coding:
- **Triggers**: Unfamiliar patterns, performance-sensitive code, external API usage
- **Action**: Pause, research, document approach in todo.md, then continue

### Exit → Enter Reviewer Loop
**Trigger**: All conditions met:
- [ ] Code compiles/builds successfully
- [ ] Tests pass
- [ ] Linter/formatter checks pass
- [ ] Task marked complete in todo.md

---

## Reviewer Loop

**Purpose**: Fresh-context review via background Task agents. Scales with change complexity.

### Step 1: Analyze Changes
Assess the implementation:
- **Volume**: Lines changed (small: <50, medium: 50-200, large: 200+)
- **Complexity**: Simple CRUD, algorithmic, concurrency, state management
- **Sensitivity**: Performance-critical? Security-sensitive? Public API?
- **Scope**: Isolated module or cross-cutting?

### Step 2: Select Reviewers

| Change Characteristics | Recommended Agents |
|------------------------|-------------------|
| Small, isolated, simple | `code-reviewer` only |
| Language-specific patterns | Add language expert (`rust-expert`, `python-expert`, `golang-expert`, `typescript-pro` etc.) |
| Auth, input validation, crypto | Add `security-auditor` |
| Hot paths, data structures, I/O | Add `performance-engineer`, `rust-performance-analyzer`, `dod-reviewer` |
| New modules, API changes, cross-cutting | Add `architect-review`, `multi-perspective-architect`, `dod-reviewer` |
| Large or complex changes | Multiple agents in parallel |

### Step 3: Launch Reviews
Provide each agent:
- Files changed with paths
- Summary of implementation and rationale
- Change analysis (volume, complexity, sensitivity)
- Specific focus areas for that agent's expertise

### Step 4: Address Findings
- Collect findings from all agents
- Implement fixes for valid issues
- Re-run build, test, and lint commands
- Document any deferred items in backlog.md

### Exit → Enter Session Close
**Trigger**: All conditions met:
- [ ] All selected reviewers have reported
- [ ] Critical/high findings addressed
- [ ] Code still builds and tests pass after fixes

---

## Session Close

### Steps
1. Update `tasks/todo.md`:
   - Mark completed tasks with [x]
   - Add any discovered work items
   - Check if archival is needed (workstream complete?)

2. Add Review entry with:
   - Date and task identifier
   - What was done
   - Key decisions made
   - Issues encountered
   - What's next

3. Final verification:
   - Build, test, and lint commands pass: `cargo build && cargo test && cargo clippy --all-targets --all-features`

4. If workstream complete, execute archival (see Archival Rules above)

### Session Completion Checklist
- [ ] **Scoping**: Task was validated before implementation
- [ ] **Implementation**: Code written, tests passing, lints clean
- [ ] **Reviews**: Appropriate agents triggered, findings addressed
- [ ] **Documentation**: todo.md updated with completed/new items
- [ ] **Session Notes**: Review entry added
- [ ] **Verification**: Final build/test/lint passes
- [ ] **Archival**: Checked if workstream complete, archived if so

### Exit → Session Complete
**Trigger**: All checklist items satisfied

---

## Quick Reference: Workflow Transitions

```
┌─────────────────┐
│ Start Session   │
└────────┬────────┘
         │ todo.md read, task selected, project builds
         ▼
┌─────────────────┐
│ Scoping Loop    │──── score 6+ or user unclear ────► STOP: Ask User
└────────┬────────┘
         │ scope clear, files known, approach selected
         ▼
┌─────────────────┐
│ Implementation  │──── build/test/lint fail ────► iterate
└────────┬────────┘
         │ build + test + lint pass
         ▼
┌─────────────────┐
│ Reviewer Loop   │──── findings need fixes ────► fix, re-verify
└────────┬────────┘
         │ reviews complete, findings addressed
         ▼
┌─────────────────┐
│ Session Close   │──── workstream complete? ────► archive
└────────┬────────┘
         │ checklist complete
         ▼
      ✅ DONE
```

---

## Principles

- Make every change as simple as possible
- Avoid massive or complex changes - each change should impact minimal code
- Check in with the user before beginning significant work
- Provide high-level explanations of changes made
- Keep todo.md focused on active work; archive aggressively
- Scoping and review effort should scale with task complexity
