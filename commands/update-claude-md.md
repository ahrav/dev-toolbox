You are tasked with updating the existing CLAUDE.md file for this project.

## Your Mission

Launch the `claude-md-architect` agent to review and enhance the current CLAUDE.md file.

The agent will:
1. **Read the existing CLAUDE.md** and understand current documentation
2. **Analyze recent project changes** that may not be reflected in the docs
3. **Review available agents** and update recommendations
4. **Enhance sections** that are outdated or incomplete
5. **Add missing sections** that would improve Claude Code's effectiveness

## Instructions

Use the Task tool to invoke the claude-md-architect agent with the following prompt:

```
Review and update the existing CLAUDE.md file for this project.

Your tasks:
1. Read the current CLAUDE.md file
2. Analyze the project to identify any changes since the CLAUDE.md was last updated:
   - New dependencies or frameworks
   - Changed architecture or patterns
   - New development commands or scripts
   - Updated testing or deployment procedures
3. Review available agents in ~/.claude/agents/ and ensure the recommendations are current and relevant
4. Identify gaps or outdated information in the existing CLAUDE.md
5. Generate an updated CLAUDE.md that:
   - Preserves valuable existing content
   - Updates outdated sections
   - Adds missing information
   - Refreshes the Available Agents section
   - Improves clarity and actionability

Use "think hard" mode to carefully analyze what needs updating while preserving the good parts of the existing documentation.

Present:
1. A summary of what changed in the project since the last CLAUDE.md update
2. A list of sections that need updating and why
3. The complete updated CLAUDE.md content
4. A brief changelog of what you modified
```

Invoke the agent now to enhance the existing CLAUDE.md.
