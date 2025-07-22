# Specification Implementation Plan Prompt

**Workflow Stage:** Implementation Planning

```
### 3. Create Task List

After the user approves the Design, create an actionable implementation plan with a checklist of coding tasks based on the requirements and design.
The tasks document should be based on the design document, so ensure it exists first.

**Constraints:**

- The model MUST create a '.github/specs/{feature_name}/tasks.md' file if it doesn't already exist
- The model MUST read and reference both the requirements.md and design.md files before creating tasks
- The model MUST return to the design step if the user indicates any changes are needed to the design
- The model MUST return to the requirement step if the user indicates that we need additional requirements
- The model MUST create an implementation plan at '.github/specs/{feature_name}/tasks.md'
- The model MUST use the following specific instructions when creating the implementation plan:

```

Convert the feature design into a series of actionable coding task prompts that will implement each step in a test-driven manner. Prioritize best practices, incremental progress, and early testing, ensuring no big jumps in complexity at any stage. Make sure that each task builds on the previous tasks, and ends with wiring things together. There should be no hanging or orphaned code that isn't integrated into a previous step. Focus ONLY on tasks that involve writing, modifying, or testing code.

Each task should be concrete enough that a coding agent can execute it without additional clarification beyond the requirements and design documents.

````

- The model MUST format the implementation plan as a numbered checkbox list with a maximum of two levels of hierarchy:
- Top-level items (like epics) should be used only when needed
- Sub-tasks should be numbered with decimal notation (e.g., 1.1, 1.2, 2.1)
- Each item must be a checkbox
- Simple structure is preferred
- The model MUST ensure each task item includes:
  - A clear, actionable objective as the task description that involves writing, modifying, or testing code
  - Additional context as sub-bullets under the task including:
    - Specific files or components to be created/modified
    - Expected inputs and outputs
    - Testing requirements for the task
  - Specific references to requirements from the requirements document (referencing granular sub-requirements, not just user stories)
  - Cross-references to relevant design sections
- The model MUST include an example task format:
  ```markdown
  ## 1. Setup and Foundation
  - [ ] 1.1. Create basic project structure and configuration files
    - Create main application entry point
    - Setup testing framework and configuration
    - Implement basic error handling infrastructure
    - **Requirements**: Addresses requirement 1.1, 1.2 from requirements.md
    - **Design Reference**: Architecture section, Component setup
    - **Testing**: Verify project builds and basic tests run
````

- The model MUST ensure that the implementation plan is a series of discrete, manageable coding steps
- The model MUST ensure each task references specific requirements from the requirements document and design sections
- The model MUST NOT include excessive implementation details that are already covered in the design document
- The model MUST assume that all context documents (feature requirements, design) will be available during implementation
- The model MUST ensure each step builds incrementally on previous steps with clear dependencies
- The model SHOULD prioritize test-driven development where appropriate, including tests as part of task definitions
- The model MUST ensure the plan covers all aspects of the design that can be implemented through code
- The model SHOULD sequence steps to validate core functionality early through code and automated tests
- The model MUST ensure that all requirements are covered by the implementation tasks with explicit traceability
- The model MUST offer to return to previous steps (requirements or design) if gaps are identified during implementation planning
- The model MUST ONLY include tasks that can be performed by a coding agent (writing code, creating tests, etc.)
- The model MUST NOT include tasks related to user testing, deployment, performance metrics gathering, or other non-coding activities
- The model MUST focus on code implementation tasks that can be executed within the development environment
- The model MUST ensure each task is actionable by a coding agent by following these guidelines:
- Tasks should involve writing, modifying, or testing specific code components
- Tasks should specify what files or components need to be created or modified
- Tasks should be concrete enough that a coding agent can execute them without additional clarification
- Tasks should focus on implementation details rather than high-level concepts
- Tasks should be scoped to specific coding activities (e.g., "Implement X function" rather than "Support X feature")
- The model MUST explicitly avoid including the following types of non-coding tasks in the implementation plan:
- User acceptance testing or user feedback gathering
- Deployment to production or staging environments
- Performance metrics gathering or analysis
- Running the application to test end to end flows. We can however write automated tests to test the end to end from a user perspective.
- User training or documentation creation
- Business process changes or organizational changes
- Marketing or communication activities
- Any task that cannot be completed through writing, modifying, or testing code
- After updating the tasks document, the model MUST ask the user "Do the tasks look good?" using the 'userInput' tool.
- The 'userInput' tool MUST be used with the exact string 'spec-tasks-review' as the reason
- The model MUST make modifications to the tasks document if the user requests changes or does not explicitly approve.
- The model MUST ask for explicit approval after every iteration of edits to the tasks document.
- The model MUST NOT consider the workflow complete until receiving clear approval (such as "yes", "approved", "looks good", etc.).
- The model MUST continue the feedback-revision cycle until explicit approval is received.
- The model MUST stop once the task document has been approved.

**This workflow is ONLY for creating design and planning artifacts. The actual implementation of the feature should be done through a separate workflow.**

- The model MUST NOT attempt to implement the feature as part of this workflow
- The model MUST clearly communicate to the user that this workflow is complete once the design and planning artifacts are created
- The model MUST inform the user that they can begin executing tasks by opening the tasks.md file, and clicking "Start task" next to task items.

```

```
