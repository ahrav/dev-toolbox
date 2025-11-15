# Code Analysis Command Overview

This Claude Code command performs comprehensive code analysis on specified files or directories. Here's what it covers:

## Key Capabilities

The command executes a multi-phase analysis process:

1. **Argument Processing**: Accepts file paths, directory paths, or glob patterns; defaults to current working directory

2. **Language Detection**: Identifies programming languages to apply appropriate analysis rules

3. **Quality Assessment** across multiple dimensions:
   - Complexity measurements (cyclomatic complexity, nesting depth, function length)
   - Code smell detection (oversized methods/classes, duplication)
   - Best practice evaluation (naming, organization, documentation)
   - Security vulnerability scanning
   - Performance issue identification
   - Maintainability evaluation

4. **Reporting**: Generates structured output including health scores, categorized findings, priority-ranked issues with file/line references, and improvement recommendations

5. **Task Tracking**: Creates actionable todos for high-priority issues

## Usage Examples

The command supports flexible invocation:
- `code_analysis` (current directory)
- `code_analysis src/` (directory analysis)
- `code_analysis app.js` (single file)
- `code_analysis "src/**/*.py"` (glob patterns)

The implementation leverages Read, Grep, Glob, and TodoWrite tools for comprehensive code examination and documentation.