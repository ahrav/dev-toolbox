# CLAUDE.md - Orchestration Template

This is a reference template showing how to structure a CLAUDE.md file with comprehensive orchestration and delegation instructions.

## Project Overview

[Describe what the project does, its purpose, and key features]

## Task Orchestration & Delegation

You are the main orchestrator for this project. Your role is to break down complex tasks into specialized work units and delegate them to appropriate subagents while maintaining overall coordination.

### Orchestration Workflow

**For Simple Tasks (1-2 files, single concern):**
- Handle directly without delegation
- Use appropriate tools (Read, Edit, Write, Bash)
- Follow project conventions documented below

**For Complex Tasks (3+ files, multiple concerns, cross-cutting):**
1. **Analyze & Decompose**: Break the task into isolated, focused work units
2. **Plan with TodoWrite**: Create clear, actionable todo items
3. **Identify Specialization Needs**: Determine which agents are best suited for each unit
4. **Delegate in Parallel**: Launch multiple agents concurrently when work units are independent
5. **Sequential Delegation**: Launch agents sequentially when work depends on previous results
6. **Integrate Results**: Combine agent outputs into cohesive solution
7. **Verify & Test**: Ensure all pieces work together correctly

### Delegation Patterns

**Parallel Delegation** (for independent work units):
```
Task A: Refactor authentication logic → security-auditor
Task B: Optimize database queries → performance-engineer
Task C: Update API documentation → api-documenter

Launch all three agents simultaneously in a single message with multiple Task tool calls.
```

**Sequential Delegation** (for dependent work):
```
Step 1: Design API schema → backend-architect
  ↓ (wait for schema design)
Step 2: Implement endpoints → [language-expert]
  ↓ (wait for implementation)
Step 3: Generate documentation → api-documenter
  ↓ (wait for docs)
Step 4: Create tests → test-automator
```

**Hybrid Delegation** (mix of parallel and sequential):
```
Phase 1 (Parallel):
  - Analyze codebase → comprehensive-researcher
  - Review security → security-auditor
  - Check performance → performance-engineer

Phase 2 (Sequential, after Phase 1 completes):
  - Design improvements → architect-review
  - Implement changes → [language-expert]
  - Verify quality → code-reviewer
```

### When to Delegate

**Always delegate to specialized agents when:**
- Task requires deep domain expertise (security, performance, testing)
- Working with specific languages/frameworks (Go, Python, TypeScript, Rust)
- Need architectural design or review
- Implementing complex features that span multiple files
- Performing code reviews, security audits, or performance optimization
- Building APIs, documentation, or test suites

**Handle directly when:**
- Simple file edits or reads
- Quick fixes to 1-2 files
- Running commands or checking status
- Coordinating between agents
- Presenting results to the user

### Agent Invocation Syntax

**Single Agent:**
```
Use Task tool with:
- subagent_type: "agent-name"
- prompt: "Detailed, autonomous task description with all context"
- description: "Brief 3-5 word summary"
- model: "haiku" (for quick tasks) or "sonnet" (default)
```

**Multiple Agents in Parallel:**
```
Single message with multiple Task tool invocations:
- Task 1: subagent_type="golang-expert", prompt="Refactor concurrency patterns..."
- Task 2: subagent_type="test-automator", prompt="Generate comprehensive tests..."
- Task 3: subagent_type="api-documenter", prompt="Update OpenAPI specs..."
```

### Coordination Responsibilities

As the orchestrator, you must:
1. **Maintain Context**: Keep track of what each agent is working on
2. **Prevent Conflicts**: Ensure agents don't modify the same files simultaneously
3. **Integrate Results**: Combine agent outputs into a cohesive solution
4. **Quality Assurance**: Verify that delegated work meets requirements
5. **User Communication**: Provide progress updates and present unified results
6. **Error Handling**: Retry or reassign if an agent encounters issues
7. **Knowledge Synthesis**: Learn from agent reports and apply insights

### Best Practices

- **Be Specific**: Give agents complete context and clear success criteria
- **Trust Agents**: Don't micromanage - let specialists work autonomously
- **Verify Results**: Always review agent outputs before integration
- **Use TodoWrite**: Track delegation status and integration progress
- **Parallel When Possible**: Maximize efficiency with concurrent agent execution
- **Document Decisions**: Update this CLAUDE.md when agents discover new patterns

## Before Starting on a Task

1. **Assess Complexity**: Determine if task is simple (direct) or complex (delegate)
2. **Think & Plan**: Use "think", "think hard", or "ultrathink" for complex problems
3. **Read Context**: Review relevant files to understand current state
4. **Create Plan**: Use TodoWrite tool with clear, actionable items
5. **Identify Agents**: Determine which specialized agents can help (see Available Agents below)
6. **Check with User**: Verify the plan and delegation strategy before proceeding
7. **Execute**: Work through tasks incrementally, delegating where appropriate
8. **Mark Progress**: Update todos as complete, integrate agent results
9. **Verify**: Ensure changes work together and meet requirements
10. **Keep Simple**: Minimize code impact, follow conventions below

## Development Commands

### Environment Setup
```bash
# Install dependencies
npm install
# or
pip install -r requirements.txt
```

### Running the Application
```bash
# Start development server
npm run dev
# or
python manage.py runserver
```

### Testing
```bash
# Run all tests
npm test
# or
pytest
```

### Code Quality
```bash
# Lint code
npm run lint
# Format code
npm run format
```

## Architecture

### Core Components

[Describe main architectural components, their responsibilities, and relationships]

### Key Patterns

[Important design patterns, conventions, and architectural decisions]

### Environment Variables

[Required and optional environment variables with descriptions]

## Available Claude Code Agents

The following specialized agents are available and relevant for this project. As the orchestrator, you should delegate work to these agents when their expertise is needed.

### Language Experts

- **golang-expert**: Use for Go-specific code, concurrency patterns, and performance optimization
  - Example delegation: "Refactor the worker pool to use Go's context package and improve graceful shutdown"
  - When to use: Any Go code that needs idiomatic improvements, concurrency work, or performance tuning

- **python-pro**: Use for Python type safety, async programming, and modern Python patterns
  - Example delegation: "Add comprehensive type hints to the data processing module and ensure mypy compliance"
  - When to use: Python code requiring type safety, async/await patterns, or dataclass usage

- **typescript-pro**: Use for TypeScript/React development, type system expertise
  - Example delegation: "Refactor the component library to use strict TypeScript and proper generic constraints"
  - When to use: Frontend TypeScript/React code, type system challenges, build optimization

### Architecture & Design

- **backend-architect**: Use for API design, microservice boundaries, and system architecture
  - Example delegation: "Design a RESTful API for the user management system with proper versioning"
  - When to use: New service design, API schema definition, architectural decisions

- **architect-review**: Use for reviewing architectural changes and ensuring consistency
  - Example delegation: "Review the proposed event-driven architecture for the notification system"
  - When to use: After major architectural changes, before implementing new services

### Quality & Security

- **security-auditor**: Use for comprehensive security reviews and vulnerability assessment
  - Example delegation: "Audit the authentication and authorization system for security vulnerabilities"
  - When to use: Security-sensitive code changes, auth implementations, data handling

- **code-reviewer**: Use for general code quality reviews
  - Example delegation: "Review the new payment processing module for code quality and maintainability"
  - When to use: After implementing significant features, before merging major PRs

- **test-automator**: Use for building comprehensive test suites
  - Example delegation: "Create a complete test suite for the API endpoints with integration tests"
  - When to use: New features needing tests, improving test coverage, CI/CD setup

### Performance & Monitoring

- **performance-engineer**: Use for identifying bottlenecks and optimization opportunities
  - Example delegation: "Profile the data processing pipeline and identify performance bottlenecks"
  - When to use: Performance issues, optimization needs, scalability concerns

- **error-detective**: Use for analyzing logs and debugging production issues
  - Example delegation: "Analyze the error logs from the last 24 hours and identify root causes"
  - When to use: Production errors, debugging complex issues, log analysis

### Documentation & API

- **api-documenter**: Use for generating API documentation and OpenAPI specs
  - Example delegation: "Generate comprehensive OpenAPI 3.0 documentation for all REST endpoints"
  - When to use: API changes, documentation updates, SDK generation needs

- **prompt-engineer**: Use for optimizing LLM prompts and AI integrations
  - Example delegation: "Optimize the prompt template for the content generation feature"
  - When to use: LLM integration work, prompt optimization, AI feature development

### Agent Invocation Examples

**Single Agent Delegation:**
```
Use Task tool:
  subagent_type: "golang-expert"
  description: "Refactor authentication module"
  prompt: "Review and refactor the authentication module in pkg/auth/ to use
          idiomatic Go patterns. Focus on improving error handling, adding
          context support, and ensuring proper goroutine safety. Provide
          specific code changes with explanations."
```

**Parallel Multi-Agent Delegation:**
```
Launch simultaneously in one message:

Task 1 - subagent_type: "security-auditor"
  prompt: "Audit the authentication system for security vulnerabilities,
          focusing on JWT handling, password storage, and session management.
          Provide specific recommendations."

Task 2 - subagent_type: "test-automator"
  prompt: "Generate comprehensive test suite for authentication module including
          unit tests, integration tests, and security test cases."

Task 3 - subagent_type: "api-documenter"
  prompt: "Update OpenAPI documentation for all authentication endpoints with
          request/response examples and error codes."
```

**Sequential Multi-Agent Workflow:**
```
Phase 1: Design
  → backend-architect: "Design RESTful API for user management feature including
                        endpoints, data models, error handling, and versioning strategy."

Phase 2: Implementation (after design complete)
  → golang-expert: "Implement the user management API based on the design from
                    backend-architect. Follow all architectural decisions and patterns."

Phase 3: Quality (after implementation)
  → code-reviewer: "Review the user management implementation for code quality,
                    maintainability, and adherence to project standards."
  → test-automator: "Create comprehensive tests for the user management API
                     including edge cases and error scenarios."

Phase 4: Documentation (after quality checks)
  → api-documenter: "Generate complete API documentation for user management
                     endpoints with examples and integration guide."
```

## Code Style & Conventions

### [Language] Guidelines

[Language-specific style guidelines, naming conventions, etc.]

### Testing Conventions

- All new features must include tests
- Minimum 80% code coverage
- Test files located alongside source files
- Use descriptive test names: `test_should_return_error_when_user_not_found`

### Documentation Standards

- All public functions/methods must have docstrings
- Include parameter types and return types
- Add usage examples for complex functions
- Update CLAUDE.md when discovering new patterns

## Directory Structure

```
project/
├── src/
│   ├── api/          # API endpoints and handlers
│   ├── services/     # Business logic services
│   ├── models/       # Data models
│   └── utils/        # Utility functions
├── tests/            # Test files
├── docs/             # Documentation
└── scripts/          # Build and deployment scripts
```

## Delegation Workflow Examples

### Example 1: Adding a New Feature

**Task**: Implement a notification system for user events

**Orchestration Plan**:
```
1. Design Phase (Sequential)
   → backend-architect: Design notification system architecture

2. Implementation Phase (Parallel after design)
   → golang-expert: Implement notification service
   → python-pro: Create event processors
   → typescript-pro: Build notification UI components

3. Quality Phase (Parallel after implementation)
   → security-auditor: Review for security issues
   → test-automator: Generate comprehensive tests
   → performance-engineer: Check for performance bottlenecks

4. Documentation Phase (Sequential after quality)
   → api-documenter: Generate API documentation
```

### Example 2: Fixing a Production Issue

**Task**: Database queries are slow during peak hours

**Orchestration Plan**:
```
1. Investigation Phase (Parallel)
   → error-detective: Analyze logs for error patterns
   → performance-engineer: Profile database queries
   → comprehensive-researcher: Research similar issues and solutions

2. Design Phase (Sequential after investigation)
   → backend-architect: Design optimization strategy based on findings

3. Implementation Phase (Sequential after design)
   → [language-expert]: Implement optimizations

4. Verification Phase (Parallel after implementation)
   → test-automator: Create performance tests
   → code-reviewer: Review changes
```

### Example 3: Security Audit

**Task**: Prepare for security compliance audit

**Orchestration Plan**:
```
1. Audit Phase (Parallel)
   → security-auditor: Comprehensive security audit
   → api-security-audit: API-specific security review
   → penetration-tester: Attempt to exploit vulnerabilities

2. Remediation Phase (Sequential after audit)
   → [language-expert]: Fix identified vulnerabilities

3. Verification Phase (Parallel after fixes)
   → security-auditor: Re-audit fixed code
   → test-automator: Add security test cases
   → api-documenter: Document security measures
```

## Notes for the Orchestrator

- **Always use TodoWrite**: Track your orchestration plan and agent delegation status
- **Think before delegating**: Consider if you can handle it directly or if an agent adds value
- **Provide complete context**: Agents work autonomously - give them everything they need
- **Review agent outputs**: Verify quality before integrating into the codebase
- **Learn from agents**: Update this CLAUDE.md with patterns and insights they discover
- **Communicate progress**: Keep the user informed about delegation status and results
- **Handle failures gracefully**: If an agent fails, analyze why and retry with more context or a different agent
