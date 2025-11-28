You are tasked with updating the existing CLAUDE.md file for this project, with focus on enhancing orchestration and delegation guidance.

## Your Mission

Launch the `claude-md-architect` agent to review and enhance the current CLAUDE.md file.

The agent will:
1. **Read the existing CLAUDE.md** and understand current documentation
2. **Analyze recent project changes** that may not be reflected in the docs
3. **Review available agents** and update recommendations with delegation patterns
4. **Enhance or add orchestration framework** if missing or incomplete
5. **Update sections** that are outdated or need better delegation guidance
6. **Add concrete workflow examples** for common tasks in this project

## Instructions

Use the Task tool to invoke the claude-md-architect agent with the following prompt:

```
Review and update the existing CLAUDE.md file for this project with enhanced orchestration and delegation framework.

Your tasks:
1. Read the current CLAUDE.md file
2. Analyze the project to identify any changes since the CLAUDE.md was last updated:
   - New dependencies or frameworks
   - Changed architecture or patterns
   - New development commands or scripts
   - Updated testing or deployment procedures
   - New agents available in ~/.claude/agents/

3. Review the orchestration framework:
   - Check if "Task Orchestration & Delegation" section exists
   - Ensure it has clear patterns for when to delegate vs. handle directly
   - Verify it includes parallel, sequential, and hybrid delegation examples
   - Add or enhance if missing or incomplete

4. Update Available Agents section:
   - Review all agents in ~/.claude/agents/
   - Add new agents that are now relevant
   - Remove agents that are no longer applicable
   - Include specific delegation examples for each agent
   - Add workflow examples for common project tasks

5. Generate an updated CLAUDE.md that:
   - Preserves valuable existing content
   - Adds comprehensive orchestration framework if missing
   - Updates outdated sections
   - Enhances agent recommendations with concrete examples
   - Includes project-specific delegation workflows
   - Improves clarity and actionability

Reference the orchestration template at ~/.claude/examples/CLAUDE.orchestration.template.md for best practices.

Use "think hard" mode to carefully analyze what needs updating while preserving the good parts of the existing documentation.

Present:
1. A summary of what changed in the project since the last CLAUDE.md update
2. A list of sections that need updating and why
3. Assessment of current orchestration framework (if any) and improvements made
4. New agents added and delegation patterns included
5. The complete updated CLAUDE.md content
6. A brief changelog of what you modified
```

Invoke the agent now to enhance the existing CLAUDE.md with better orchestration capabilities.
