# dependency-mapper Command Documentation

The **dependency-mapper** is a CLI tool designed to "Map and analyze project dependencies" by examining code relationships, git history, and Linear tasks.

## Core Capabilities

The command identifies blockers and circular dependencies while determining optimal task sequencing. It accepts queries like:
- `claude "Show dependency map for task LIN-123"`
- `claude "Check for circular dependencies in the codebase"`
- `claude "What's the optimal order to complete tasks in sprint SPR-45?"`

## Technical Implementation

**Code Analysis Methods:**
- Extracts import/require statements from JavaScript, TypeScript, and Python files
- Scans comments for dependency indicators (TODO, FIXME, NOTE)
- Searches Linear's API for task relationships and mentions

**Graph Construction:**
The tool builds a dependency graph structure with methods for:
- Adding dependencies with type classification
- Detecting cycles using depth-first search
- Performing topological sorting for execution ordering

**Visualization Formats:**
- ASCII tree hierarchies showing task dependencies
- Mermaid diagrams with color-coded task statuses
- Dependency matrices mapping relationships between items

## Output Features

Analysis results include:
- Dependency trees with completion status indicators
- Critical path identification for sprint planning
- Task distribution across team members
- File-to-task mapping showing which code relates to which work items
- Actionable recommendations for blocking issues

The tool gracefully handles missing Linear access by falling back to code-only analysis and validates all referenced tasks exist before processing.