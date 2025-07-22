# Specification Requirements Clarification Prompt

**Workflow Stage:** Requirements Gathering

````
### 1. Requirement Gathering

First, generate an initial set of requirements in EARS format based on the feature idea, then iterate with the user to refine them until they are complete and accurate.

Don't focus on code exploration in this phase. Instead, just focus on writing requirements which will later be turned into
a design.

**Constraints:**

- The model MUST create a '.github/specs/{feature_name}/requirements.md' file if it doesn't already exist
- The model MUST generate an initial version of the requirements document based on the user's rough idea WITHOUT asking sequential questions first
- The model MUST format the initial requirements.md document with:
  - A clear introduction section that summarizes the feature
  - A hierarchical numbered list of requirements where each contains:
    - A user story in the format "As a [role], I want [feature], so that [benefit]"
    - A numbered list of acceptance criteria in EARS format (Easy Approach to Requirements Syntax)
  - Example format:
    ```markdown
    ## 1. User Authentication
    **User Story**: As a user, I want to log into the system, so that I can access my personal data.

    **Acceptance Criteria**:
    1.1. WHEN a user enters valid credentials, THE SYSTEM SHALL authenticate the user within 2 seconds
    1.2. WHEN a user enters invalid credentials, THE SYSTEM SHALL display an error message
    1.3. THE SYSTEM SHALL lock the account after 3 failed login attempts
    1.4. IF account lockout occurs, THEN THE SYSTEM SHALL send an email notification to the user

    ## 2. Data Display
    **User Story**: As a logged-in user, I want to view my dashboard, so that I can see my current status.

    **Acceptance Criteria**:
    2.1. THE SYSTEM SHALL display the user dashboard within 1 second of successful login
    2.2. WHEN data is loading, THE SYSTEM SHALL show a loading indicator
    2.3. IF data fails to load, THEN THE SYSTEM SHALL display an error message with retry option
    ```
- The model SHOULD consider edge cases, user experience, technical constraints, and success criteria in the initial requirements
- The model SHOULD specifically consider the following types of edge cases when generating requirements:
  - Security considerations (authentication, authorization, data protection)
  - Performance constraints (response times, load handling, scalability)
  - Error handling and recovery scenarios
  - Accessibility requirements for users with disabilities
  - Mobile responsiveness and cross-platform compatibility
  - Data validation and input sanitization
  - Network connectivity issues and offline scenarios
  - Browser compatibility and backwards compatibility
- After updating the requirement document, the model MUST ask the user "Do the requirements look good? If so, we can move on to the design." using the 'userInput' tool.
- The 'userInput' tool MUST be used with the exact string 'spec-requirements-review' as the reason
- The model MUST make modifications to the requirements document if the user requests changes or does not explicitly approve
- The model MUST ask for explicit approval after every iteration of edits to the requirements document
- The model MUST NOT proceed to the design document until receiving clear approval (such as "yes", "approved", "looks good", etc.)
- The model MUST continue the feedback-revision cycle until explicit approval is received
- The model SHOULD suggest specific areas where the requirements might need clarification or expansion
- The model MAY ask targeted questions about specific aspects of the requirements that need clarification
- The model MAY suggest options when the user is unsure about a particular aspect
- The model MUST proceed to the design phase after the user accepts the requirements and provides explicit approval

**EARS Format Guidelines:**
EARS (Easy Approach to Requirements Syntax) follows these patterns:
- WHEN [condition], THE SYSTEM SHALL [action]
- THE SYSTEM SHALL [action] WITHIN [time constraint]
- IF [condition], THEN THE SYSTEM SHALL [action]
- THE SYSTEM SHALL [action] FOR [scope/range]
- WHILE [state], THE SYSTEM SHALL [action]
````
