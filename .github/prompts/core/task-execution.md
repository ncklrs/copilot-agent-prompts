# Specification Task Execution Prompt

**Workflow Stage:** Task Execution

```
Follow these instructions for user requests related to spec tasks. The user may ask to execute tasks or just ask general questions about the tasks.

## Pre-Execution Requirements
- Before executing any tasks, ALWAYS ensure you have read the specs requirements.md, design.md and tasks.md files from the `.github/specs/{feature_name}/` directory
- Executing tasks without the requirements or design context will lead to inaccurate implementations
- Verify that the task you're about to execute exists in the tasks.md file and understand its context within the overall implementation plan

## Task Execution Instructions
- Look at the specific task details in the task list, including any sub-bullets with additional context
- If the requested task has sub-tasks, always start with the sub-tasks in the order specified
- Only focus on ONE task at a time. Do not implement functionality for other tasks, even if they seem related
- Verify your implementation against any requirements specified in the task details and cross-reference with the requirements.md file
- Ensure your implementation aligns with the design patterns and architecture specified in design.md
- Include appropriate testing as specified in the task or as required by the testing strategy in the design document
- Once you complete the requested task, stop and let the user review. DO NOT automatically proceed to the next task in the list
- If the user doesn't specify which task they want to work on, look at the task list for that spec and make a recommendation for the next logical task to execute based on dependencies and current progress

## Quality Assurance
- Each task completion should include:
  - Implementation of the specified functionality
  - Appropriate tests (unit, integration, or other as specified)
  - Documentation updates if required by the task
  - Verification that the implementation meets the acceptance criteria from the related requirements
- Run tests after implementation to ensure the task is properly completed
- If a task fails or cannot be completed as specified, explain the issue and suggest alternatives or request clarification

## Important Reminders
Remember, it is VERY IMPORTANT that you only execute one task at a time. Once you finish a task, stop and wait for user review. Don't automatically continue to the next task without the user explicitly asking you to do so. This ensures proper oversight and allows for course correction if needed.

## Task Completion Process
- After implementing a task, verify all requirements are met:
  - Functionality works as specified
  - Tests pass successfully
  - Code follows design patterns from design.md
  - Acceptance criteria from requirements.md are satisfied
- Provide a summary of what was completed, including:
  - Files created or modified
  - Tests implemented and their results
  - Any issues encountered and how they were resolved
  - Confirmation that the task meets its specified requirements
- Mark the task as complete in the tasks.md file by checking the checkbox: `- [x] Task description`
- Wait for user review and approval before proceeding to any other tasks
- If the user identifies issues, address them before marking the task as complete

## Task Questions
The user may ask questions about tasks without wanting to execute them. Don't always start executing tasks in cases like this.

For example, the user may want to know what the next task is for a particular feature. In this case, just provide the information and don't start any tasks.
```
