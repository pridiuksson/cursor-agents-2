# Prompt: Generate Cursor Rules Based on Monorepo Agent Pattern

## Context

You are helping create Cursor AI agent rules for a new project. Use the QA.tech Monorepo Agent presentation as inspiration and adapt it to your project's specific needs.

## Reference Material

Review the following file: `monorepo-agent-presentation.md`

This document demonstrates:

- A unified agent role with clear purpose and principles
- A systematic workflow (5-step process)
- Pattern-based routing to specialized guides
- Integration with external tools (MCP, observability)
- Real-world examples showing the workflow in action

## Your Task

Create a similar agent role structure for your project by:

### Step 1: Understand Your Project Context

Analyze your codebase to identify:

1. **Project Structure**
   - What are your main apps/services/modules?
   - What are your shared packages/libraries?
   - How is code organized? (monorepo, multi-repo, single repo?)

2. **Common Development Scenarios**
   - What types of work do developers do most often?
   - What are the recurring patterns? (e.g., API endpoints, database changes, UI components)
   - What are the common pain points or areas where mistakes happen?

3. **Tooling & Integration**
   - What external tools do you use? (issue trackers, observability, CI/CD)
   - What MCP servers or APIs are available?
   - What debugging/observability tools exist?

4. **Security & Architecture Principles**
   - What are your non-negotiable principles? (e.g., multi-tenant isolation, API boundaries)
   - What patterns must always be followed?
   - What are common anti-patterns to avoid?

### Step 2: Extract Key Components from Reference

From the monorepo agent presentation, identify these components:

1. **Role Definition**
   - Purpose statement
   - Core capabilities
   - First principles (3-5 key rules)

2. **Workflow Structure**
   - Numbered steps (typically 4-6 steps)
   - Each step has clear purpose and actions
   - Decision points with clear criteria

3. **Pattern System**
   - Common scenarios mapped to pattern guides
   - Pattern discovery protocol
   - Reference implementation approach

4. **Tool Integration**
   - MCP tools used
   - External APIs/tools
   - Observability integration

5. **Example Workflow**
   - Real scenario from start to finish
   - Shows each step in action
   - Demonstrates tool usage

### Step 3: Create Your Agent Role Document

Create a file: `.cursor/rules/agents/your-project-agent.mdc`

Structure it as follows:

```markdown
---
description: [One-line description of your agent role]
alwaysApply: true
---

## [Your Project] Agent

**Purpose:** [Clear statement of what this agent does and why]

### Core Purpose

The agent acts as a **[type of assistant]** that:

- [Capability 1]
- [Capability 2]
- [Capability 3]

### First Principles

1. **[Principle 1]**: [Why it matters]
2. **[Principle 2]**: [Why it matters]
3. **[Principle 3]**: [Why it matters]

### Common Scenarios

**[Scenario Type 1]** (e.g., API Development)

- When: [Trigger conditions]
- Follow: `@rules/patterns/[pattern-name].mdc`
- Tools: [Tool priority order]

**[Scenario Type 2]** (e.g., Database Changes)

- When: [Trigger conditions]
- Follow: `@rules/patterns/[pattern-name].mdc`
- Tools: [Tool priority order]

### Core Workflow

1. **[Step 1 Name]**
   - [Action 1]
   - [Action 2]
   - [Decision point if needed]

2. **[Step 2 Name]**
   - [Action 1]
   - [Action 2]

[Continue for all steps...]

### Definition of Done

- [Criterion 1]
- [Criterion 2]
- [Criterion 3]

### Tooling References

- **MCP Guides:** `@rules/mcp/[tool-name].mdc`
- **Pattern Guides:** `@rules/patterns/[pattern-name].mdc`
- **Protocols:** `@rules/protocols/[protocol-name].mdc`
```

### Step 4: Create Supporting Pattern Documents

For each common scenario, create a pattern guide:

`.cursor/rules/patterns/[scenario-name].mdc`

```markdown
---
description: [Pattern description]
---

## Pattern: [Scenario Name]

## When to Use

- [Condition 1]
- [Condition 2]

## Approach

[Step-by-step approach]

## Tools & Integration

- [Tool 1]: [How to use]
- [Tool 2]: [How to use]

## Example

[Concrete example showing the pattern]
```

### Step 5: Create Workflow Diagram

Create a Mermaid flowchart showing:

- Entry point (what triggers the agent)
- Decision points (how to route to patterns)
- Step flow (how steps connect)
- Exit points (completion criteria)

Use the monorepo agent diagram as a template, but adapt:

- Decision criteria to your scenarios
- Tool integrations to your tools
- Steps to your workflow

### Step 6: Create Real Example

Document a complete example showing:

- Starting point (ticket, request, etc.)
- Each workflow step executed
- Tool usage at each step
- Final outcome

Make it realistic and specific to your project.

## Key Principles to Follow

1. **Be Specific**: Don't use generic terms. Reference actual files, tools, and patterns from your project.

2. **Show, Don't Tell**: Include code examples, file paths, and tool commands specific to your project.

3. **Pattern-First**: Identify existing patterns before creating new ones. The agent should follow, not invent.

4. **Tool Integration**: Explicitly show how to use your tools (MCP, APIs, CLI commands).

5. **Decision Clarity**: Make decision points unambiguous with clear criteria.

6. **Real Examples**: Use actual scenarios from your project, not hypothetical ones.

## Questions to Answer

As you create your rules, ensure you can answer:

1. **What triggers this agent?** (ticket types, request patterns, file changes)
2. **How does it discover patterns?** (code search, file structure, existing implementations)
3. **What tools does it use?** (MCP servers, APIs, CLI tools, observability)
4. **How does it verify work?** (tests, linting, manual checks)
5. **What are the quality gates?** (approval points, verification steps)
6. **How does it integrate with your workflow?** (PRs, tickets, deployments)

## Output Structure

Create these files:

```
.cursor/rules/
├── agents/
│   └── your-project-agent.mdc          # Main agent role
├── patterns/
│   ├── [scenario-1].mdc                 # Pattern guides
│   ├── [scenario-2].mdc
│   └── [scenario-n].mdc
├── protocols/
│   ├── [workflow-1].mdc                 # Cross-cutting workflows
│   └── [workflow-2].mdc
└── mcp/
    └── [tool-name].mdc                  # Tool integration guides
```

## Validation Checklist

Before finalizing, verify:

- [ ] Agent role has clear purpose and principles
- [ ] Workflow steps are actionable and specific
- [ ] Common scenarios map to pattern guides
- [ ] Pattern guides include real examples
- [ ] Tool integration is documented
- [ ] Workflow diagram accurately represents the process
- [ ] Real example demonstrates the full workflow
- [ ] All file paths and commands are project-specific
- [ ] Decision points have clear criteria
- [ ] Quality gates are defined

## Example Adaptation

**If your project is a microservices architecture:**

- Common scenarios might be: "Add new API endpoint", "Add new service", "Update shared library"
- Patterns might reference: OpenAPI specs, service discovery, API gateway configs
- Tools might include: Kubernetes, service mesh, API documentation generators

**If your project is a mobile app:**

- Common scenarios might be: "Add new screen", "Add new API integration", "Update design system"
- Patterns might reference: Navigation structure, state management, API client patterns
- Tools might include: App stores, build systems, design tools

**If your project is a data platform:**

- Common scenarios might be: "Add new data pipeline", "Add new data model", "Update ETL process"
- Patterns might reference: Schema definitions, pipeline templates, data quality checks
- Tools might include: Data warehouses, orchestration tools, monitoring dashboards

## Next Steps

1. Read `monorepo-agent-presentation.md` completely
2. Analyze your codebase structure and common patterns
3. Create the agent role document following the structure above
4. Create pattern guides for your common scenarios
5. Create a workflow diagram
6. Document a real example
7. Test the rules by having the agent follow them on a real task
8. Iterate based on what works and what doesn't

## Remember

The goal is not to copy the QA.tech structure exactly, but to:

- Understand the principles behind it
- Adapt it to your project's specific needs
- Create something that helps your team work more effectively
- Make it maintainable and extensible

Good luck! 🚀
