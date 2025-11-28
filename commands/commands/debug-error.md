# Systematically Debug and Fix Errors - Command File

This debugging utility provides a comprehensive 18-step methodology for resolving errors systematically.

## Overview

The command guides users through structured error resolution, beginning with "Error Information Gathering" and progressing through investigation, root cause identification, and prevention measures.

## Key Phases

**Investigation Phase** includes:
- Collecting error messages, stack traces, and environmental context
- Reproducing the error consistently with minimal test cases
- Analyzing call chains from stack traces
- Examining code context and recent changes

**Analysis Phase** covers:
- Forming hypotheses about potential causes (null references, type mismatches, race conditions, etc.)
- Setting up debugging tools and breakpoints
- Testing hypotheses methodically
- Validating input data and edge cases

**Resolution Phase** involves:
- Identifying root causes and their scope
- Designing fixes with proper error handling
- Testing against original cases and regressions
- Implementing defensive programming measures

**Prevention Phase** emphasizes:
- Adding unit and integration tests
- Improving logging and error handling
- Setting up monitoring and alerts
- Documenting findings and updating team processes

## Documentation Requirements

The methodology concludes by stressing the importance of "detailed notes throughout the debugging process" and documenting investigations to share knowledge with teams and prevent future similar issues.