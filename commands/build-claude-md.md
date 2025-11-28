You are tasked with creating a CONCISE, focused CLAUDE.md file for this project following Anthropic's best practices.

## Your Mission

Launch the `claude-md-architect` agent to analyze this project and generate a concise CLAUDE.md file focused on PROJECT-SPECIFIC information.

The agent will:
1. **Analyze** the project structure, tech stack, and architecture
2. **Identify relevant agents** from ~/.claude/agents/ for this specific project
3. **Generate a CONCISE CLAUDE.md** (target: 80-150 lines) focused on what's unique to this project
4. **Create separate documentation files** for detailed content in .claude/docs/

## Key Principles (From Anthropic Best Practices)

**MUST FOLLOW**:
- "Keep the file concise and human-readable"
- "Don't add extensive content without testing effectiveness"
- "Avoid overly complex or verbose instructions"
- Focus on PROJECT-SPECIFIC information only

**What Belongs in CLAUDE.md**:
- Common bash commands
- Core files and utilities
- Code style guidelines specific to THIS project
- Testing instructions
- Project-specific gotchas
- Brief list of relevant agents with examples

**What Goes in .claude/docs/** (for large projects):
- Detailed architecture
- API patterns
- Testing strategy
- Deployment procedures
- Orchestration patterns

## Instructions

Use the Task tool to invoke the claude-md-architect agent with the following prompt:

```
Analyze this project and generate a CONCISE CLAUDE.md file following Anthropic's best practices.

CRITICAL: Keep CLAUDE.md concise (80-150 lines). Follow the template at ~/.claude/examples/CLAUDE.template.md

Your tasks:
1. Analyze the project:
   - Tech stack and frameworks
   - Key files and directories
   - Testing setup
   - Project-specific patterns

2. Identify relevant agents:
   - Only list agents that are RELEVANT to this specific project
   - Provide 1-2 concrete examples per agent
   - Keep it brief

3. Generate CONCISE CLAUDE.md with:
   - Project overview (2-3 sentences)
   - Quick start commands
   - Architecture overview (not details)
   - Code style specific to THIS project
   - Brief list of relevant agents
   - Project-specific gotchas/notes
   - Links to .claude/docs/ for details

4. For larger projects, create .claude/docs/ with:
   - architecture.md - Detailed system design
   - orchestration.md - Agent delegation patterns
   - api-patterns.md - API conventions
   - testing-guide.md - Testing strategy

5. Assessment:
   - If project is small/medium: Single concise CLAUDE.md
   - If project is large: Concise CLAUDE.md + .claude/docs/

Reference templates:
- CLAUDE.md: ~/.claude/examples/CLAUDE.template.md
- Docs: ~/.claude/examples/docs/

Present your findings with:
1. Project size assessment (small/medium/large)
2. Recommended agents and brief rationale
3. The CONCISE CLAUDE.md content (80-150 lines)
4. If applicable: Contents of .claude/docs/ files
5. Placement recommendation
```

Invoke the agent now to produce a concise, effective CLAUDE.md following best practices.
