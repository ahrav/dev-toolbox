You are tasked with creating an ideal CLAUDE.md file for this project with comprehensive orchestration and delegation instructions.

## Your Mission

Launch the `claude-md-architect` agent to perform a deep, comprehensive analysis of this project and generate an optimal CLAUDE.md file that establishes Claude as the main orchestrator with clear delegation patterns.

The agent will:
1. **Deeply analyze** the project structure, tech stack, and architecture
2. **Review all available agents** in ~/.claude/agents/ and match them to this project
3. **Generate a comprehensive CLAUDE.md** with orchestration framework and project-specific guidance
4. **Provide delegation patterns** showing when and how to use specialized agents
5. **Include concrete examples** of single-agent, parallel, and sequential workflows

## Instructions

Use the Task tool to invoke the claude-md-architect agent with the following prompt:

```
Perform a comprehensive analysis of this project and generate an ideal CLAUDE.md file with full orchestration and delegation framework.

Take your time to:
1. Explore the entire codebase systematically using parallel searches
2. Identify the tech stack, frameworks, testing tools, and architecture patterns
3. Review all available agents in ~/.claude/agents/ and determine which are relevant for this project
4. Generate a complete, production-ready CLAUDE.md file that includes:

   **Core Sections:**
   - Project overview and purpose
   - **Task Orchestration & Delegation framework** (instructions for Claude as orchestrator)
   - Before Starting Tasks workflow (with delegation assessment)
   - Development commands (setup, run, test, lint, build)
   - Architecture description and key patterns

   **Agent Integration:**
   - **Available Agents section** with project-specific recommendations
   - When to delegate vs. handle directly
   - Agent invocation syntax and examples
   - Single-agent, parallel, and sequential delegation patterns
   - Concrete workflow examples for this specific project

   **Additional Guidance:**
   - Code style and conventions
   - Directory structure
   - Project-specific best practices
   - Coordination responsibilities for the orchestrator

The CLAUDE.md should establish Claude as the intelligent orchestrator who:
- Breaks down complex tasks into isolated work units
- Delegates to specialized agents when their expertise is needed
- Handles simple tasks directly without unnecessary delegation
- Coordinates parallel and sequential agent workflows
- Integrates agent results into cohesive solutions

Reference the orchestration template at ~/.claude/examples/CLAUDE.orchestration.template.md for structure and patterns.

Use "ultrathink" mode - be thorough and take all the time needed to create an exceptional CLAUDE.md that will significantly improve Claude Code's effectiveness on this project.

Present your findings with:
1. A summary of the project characteristics discovered
2. A list of recommended agents and rationale for each
3. Suggested delegation workflows for common tasks in this project
4. The complete CLAUDE.md content ready to save
5. Recommendations for placement (root, parent directory, etc.)
```

Invoke the agent now and let it work autonomously to produce the best possible orchestration-enabled CLAUDE.md for this project.
