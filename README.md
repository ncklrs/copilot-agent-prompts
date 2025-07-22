# Github Copilot Agent Prompting Workflow

A collection of structured prompts and workflows for AI-powered software development, designed to guide autonomous coding agents through comprehensive feature development lifecycles.

## Overview

This repository contains a systematic approach to software development using AI agents. It provides structured prompts that guide AI models through the complete software development process, from requirements gathering to task execution.

## Repository Organization

### Core Prompts (`.github/prompts/core/`)

Essential workflow prompts that are always available:

- Core specification-driven development workflow
- Basic requirements, design, implementation, and execution prompts
- Hook creation and event-driven automation

### Enhanced Prompts (`.github/prompts/enhanced/`)

Advanced workflow capabilities organized by category:

- **Validation**: Advanced validation and testing strategies
- **Coordination**: Cross-feature integration and evolution management
- **Analysis**: Performance, security, and technical debt assessment
- **Documentation**: Multi-format documentation generation
- **Process**: Process improvement and retrospectives

**Quick Access**: Use the [Prompt Selector](tools/prompt-selector.md) for slash commands and selective inclusion.

## Workflow Stages

The system implements a 5-stage workflow for feature development:

### 1. Requirements Clarification

- **File**: `.github/spec-requirements-clarification.md`
- **Purpose**: Generate and iterate on feature requirements using EARS format (Easy Approach to Requirements Syntax)
- **Output**: Creates `requirements.md` with user stories and acceptance criteria
- **Process**: AI generates initial requirements, user reviews and approves before proceeding

### 2. Design Document Creation

- **File**: `.github/spec-design-document.md`
- **Purpose**: Develop comprehensive technical design based on approved requirements
- **Output**: Creates `design.md` with architecture, components, data models, and testing strategy
- **Process**: Includes research phase and iterative approval cycle

### 3. Implementation Planning

- **File**: `.github/spec-implementation-plan.md`
- **Purpose**: Break down design into actionable coding tasks
- **Output**: Creates `tasks.md` with numbered checklist of implementation steps
- **Focus**: Test-driven development with incremental progress

### 4. Task Execution

- **File**: `.github/spec-task-execution.md`
- **Purpose**: Guide AI agents through individual task implementation
- **Process**: One task at a time execution with human oversight
- **Focus**: Code writing, modification, and testing only

### 5. Hook Creation

- **File**: `.github/hook-creation.md`
- **Purpose**: Create configuration files that map file events to AI agent operations
- **Output**: Hook configuration files for automated workflows
- **Use Case**: Event-driven development automation

## Key Features

### Structured Workflow

- Each stage has specific constraints and requirements
- Clear approval gates between stages
- Iterative feedback and revision cycles
- Focus on incremental, manageable progress

### Test-Driven Development

- Emphasis on early testing and validation
- Code tasks prioritize testing alongside implementation
- No orphaned or unintegrated code

### Human Oversight

- Explicit approval required at each stage
- User review before proceeding to next phase
- Clear communication of stage completion

### File Organization

All artifacts are organized under `.github/specs/{feature_name}/`:

- `requirements.md` - Feature requirements and user stories
- `design.md` - Technical design and architecture
- `tasks.md` - Implementation task checklist

## Usage

### Getting Started with Requirements

To begin using the spec-driven workflow, start with requirements clarification:

#### Quick Start

1. **Create a spec directory** for your feature:

   ```bash
   mkdir -p .github/specs/your-feature-name
   ```

2. **Create an initial requirements file**:

   ```bash
   echo "# Feature: Your Feature Name" > .github/specs/your-feature-name/requirements.md
   echo "Brief description of what you want to build..." >> .github/specs/your-feature-name/requirements.md
   ```

3. **Use the requirements clarification prompt** (`.github/spec-requirements-clarification.md`) to:
   - Generate structured requirements in EARS format
   - Create proper user stories and acceptance criteria
   - Iterate until requirements are complete and approved

#### Alternative: Hook-Driven Workflow

If you have the hooks installed, simply creating or modifying a `requirements.md` file will automatically trigger the appropriate workflow guidance.

### Adding to Your Workspace

#### Option 1: Copy Prompts to Your Project

```bash
# Copy the workflow prompts to your project
cp -r .github/ /path/to/your-project/
```

#### Option 2: Reference as Submodule

```bash
# Add as git submodule for easy updates
git submodule add https://github.com/ncklrs/vscode-agent-prompts .github/workflows/vscode-agent-prompts
```

#### Option 3: User Profile Integration

Add to your global AI assistant configuration:

```yaml
# ~/.ai-assistant/config.yaml
workflows:
  spec_driven:
    prompts_path: "/path/to/vscode-agent-prompts/.github/"
    auto_trigger: true
    default_workflow: "spec-requirements-clarification"
```

### Workflow Process

1. **Start with Requirements**: Use the requirements clarification prompt to define what you want to build
2. **Design Phase**: Create technical design based on approved requirements
3. **Planning**: Break down design into coding tasks
4. **Execution**: Implement tasks one at a time
5. **Automation**: Create hooks for event-driven workflows

## Deep Dive: Spec-Driven AI Coding

### Philosophy

Spec-driven AI coding represents a paradigm shift from ad-hoc AI assistance to systematic, structured development. Instead of asking AI to "build a feature," this approach breaks down development into discrete, manageable phases with clear deliverables and approval gates.

### Key Principles

#### 1. **Separation of Concerns**

- **Requirements Phase**: Focus purely on _what_ needs to be built, not _how_
- **Design Phase**: Define _how_ the system will work, with research and architecture
- **Implementation Phase**: Break down _how_ into discrete coding tasks
- **Execution Phase**: Focus on implementing one task at a time

#### 2. **Human-AI Collaboration**

- AI generates initial artifacts (requirements, design, tasks)
- Humans review, refine, and approve before proceeding
- Clear feedback loops prevent AI from making incorrect assumptions
- Explicit approval gates ensure alignment at each stage

#### 3. **Traceability and Accountability**

- Every design decision traces back to specific requirements
- Every task references both requirements and design elements
- Clear documentation trail from initial idea to final implementation
- Enables easy maintenance and future modifications

#### 4. **Incremental Progress**

- No "big bang" implementations
- Each task builds on previous work
- Early validation through testing
- Reduces risk of major rework

### Benefits Over Traditional AI Coding

#### **Traditional Approach Challenges:**

- AI makes assumptions about requirements
- Inconsistent code quality and architecture
- Difficult to maintain or extend AI-generated code
- No clear process for handling complex features
- Limited collaboration between team members

#### **Spec-Driven Advantages:**

- **Predictable Quality**: Consistent process ensures reliable outcomes
- **Maintainable Code**: Well-documented architecture and clear task breakdown
- **Team Collaboration**: Multiple developers can work on different tasks
- **Scalability**: Process works for both simple features and complex systems
- **Risk Reduction**: Early validation prevents costly mistakes
- **Knowledge Transfer**: Complete documentation trail

### When to Use Spec-Driven Development

#### **Ideal For:**

- Complex features requiring multiple components
- Team projects with multiple developers
- Features with unclear or evolving requirements
- Systems requiring high reliability or maintainability
- Projects where documentation is important
- Learning environments where process matters

#### **Consider Alternatives For:**

- Simple bug fixes or minor tweaks
- Rapid prototyping or proof-of-concepts
- Well-understood, repetitive tasks
- Emergency fixes requiring immediate action

### Advanced Usage Patterns

#### **Multi-Feature Coordination**

```
.github/specs/
├── user-authentication/
│   ├── requirements.md
│   ├── design.md
│   └── tasks.md
├── data-dashboard/
│   ├── requirements.md
│   ├── design.md
│   └── tasks.md
└── notification-system/
    ├── requirements.md
    ├── design.md
    └── tasks.md
```

#### **Cross-Feature Dependencies**

- Design documents can reference other features' specifications
- Tasks can depend on completion of tasks from other features
- Requirements can specify integration points between features

#### **Version Control Integration**

- Each phase creates specific commits with clear messages
- Pull requests can be organized around spec phases
- Code reviews focus on task-level changes rather than entire features

### Measuring Success

#### **Process Metrics:**

- Time from initial idea to approved requirements
- Design iteration cycles before approval
- Task completion rate and velocity
- Defect rate in completed tasks

#### **Quality Metrics:**

- Requirements coverage by design elements
- Design coverage by implementation tasks
- Test coverage of implemented functionality
- Post-implementation requirement satisfaction

## Constraints and Guidelines

### Requirements Stage

- Must use EARS format for acceptance criteria
- User stories follow: "As a [role], I want [feature], so that [benefit]"
- No code exploration in this phase
- Focus purely on requirements definition

### Design Stage

- Must include: Overview, Architecture, Components, Data Models, Error Handling, Testing Strategy
- Research-driven approach with cited sources
- Mermaid diagrams when appropriate
- Addresses all requirements from previous stage

### Implementation Stage

- Maximum two levels of task hierarchy
- Each task must reference specific requirements
- Focus only on coding activities (no deployment, user testing, etc.)
- Incremental approach with early validation

### Task Execution

- One task at a time execution
- Must read requirements, design, and tasks before starting
- Stop after each task for user review
- No automatic progression to next task

## File Structure

```
.github/
├── hook-creation.md                    # Hook creation workflow
├── spec-requirements-clarification.md  # Requirements gathering
├── spec-design-document.md            # Design document creation
├── spec-implementation-plan.md        # Task planning
└── spec-task-execution.md             # Task execution

hooks/                                  # Automated workflow triggers
├── spec-requirements-hook.yaml        # Requirements workflow automation
├── spec-design-hook.yaml              # Design workflow automation
├── spec-implementation-plan-hook.yaml # Planning workflow automation
├── spec-task-execution-hook.yaml      # Execution workflow automation
├── spec-workflow-init-hook.yaml       # Workflow initialization
└── spec-quality-assurance-hook.yaml   # Quality validation

specs/                                  # Example: Feature specifications
└── {feature-name}/
    ├── requirements.md                 # EARS format requirements
    ├── design.md                      # Technical design document
    └── tasks.md                       # Implementation task checklist
```

## Installation and Setup

### For Individual Use

1. **Clone or download** this repository
2. **Copy the `.github/` directory** to your project root
3. **Install hooks** (if using automated workflows):
   ```bash
   cp hooks/* .github/hooks/
   ```
4. **Configure your AI assistant** to use the workflow prompts

### For Team/Organization Use

1. **Fork this repository** for your organization
2. **Customize prompts** for your specific needs and coding standards
3. **Set up organization-wide hooks** for automatic workflow triggering
4. **Train team members** on the spec-driven process
5. **Establish review processes** for each workflow stage

### Integration with Popular AI Tools

#### GitHub Copilot

- Use prompts as system messages in Copilot Chat
- Reference specific workflow files when starting new features
- Leverage hooks for automatic workflow suggestions

#### ChatGPT/Claude

- Copy prompt content as system instructions
- Upload workflow files as context documents
- Use for requirements brainstorming and design review

#### Custom AI Assistants

- Integrate prompts into your AI tool's workflow system
- Set up automatic triggering based on file changes
- Configure context loading for relevant specification files

## Target Users

- Software development teams using AI coding assistants
- Organizations implementing AI-driven development workflows
- Developers seeking structured approaches to feature development
- Teams looking to standardize AI agent interactions

## Benefits

- **Consistency**: Standardized approach across all feature development
- **Quality**: Built-in review cycles and approval gates
- **Traceability**: Clear connection from requirements to implementation
- **Maintainability**: Structured documentation and incremental progress
- **Automation**: Hook system enables event-driven development

## Contributing

This is a prompt engineering project focused on creating effective AI agent workflows. Contributions should maintain the structured approach and clear constraint definitions that make these prompts effective for AI agents.
# rri-dev-prompts
