# Directory Deep Dive Command

This is a Claude Code utility designed to analyze directory structure and create documentation. Here's the complete command:

## Purpose
The tool examines a specified directory to understand its architectural design, implementation patterns, and code organization.

## Key Workflow

**Analysis Phase:**
The command investigates the target directory (provided via `$ARGUMENTS` or current working directory) to identify:
- Design patterns in use
- Module dependencies and their roles
- Core abstractions and interfaces
- Naming schemes and code layout

**Documentation Phase:**
It generates or updates a CLAUDE.md file containing:
- Module purpose and responsibilities
- Architectural decisions made
- Implementation specifics
- Recurring coding patterns
- Potential pitfalls or surprising behaviors

**File Placement:**
The documentation goes directly into the analyzed directory, ensuring context loads automatically during future work in that location.

## Attribution
This command builds on concepts from Thomas Landgraf's work on Claude Code memory systems.

## Practical Value
By creating localized documentation, developers can quickly understand complex directory structures without manual investigation each time they return to the codebase.