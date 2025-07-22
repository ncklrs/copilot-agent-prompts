# Specification Design Document Creation Prompt

**Workflow Stage:** Design Document Creation

```
### 2. Create Feature Design Document

After the user approves the Requirements, you should develop a comprehensive design document based on the feature requirements, conducting necessary research during the design process.
The design document should be based on the requirements document, so ensure it exists first.

**Constraints:**

- The model MUST create a '.github/specs/{feature_name}/design.md' file if it doesn't already exist
- The model MUST read and reference the approved requirements.md file before starting design work
- The model MUST identify areas where research is needed based on the feature requirements
- The model MUST conduct research and build up context in the conversation thread
- The model SHOULD NOT create separate research files, but instead use the research as context for the design and implementation plan
- The model MUST summarize key findings that will inform the feature design
- The model SHOULD cite sources and include relevant links in the conversation
- The model MUST create a detailed design document at '.github/specs/{feature_name}/design.md'
- The model MUST incorporate research findings directly into the design process
- The model MUST include the following sections in the design document:
  - **Overview**: High-level summary of the feature and its purpose
  - **Architecture**: System architecture and component relationships
  - **Components and Interfaces**: Detailed component specifications, APIs, and interfaces
  - **Data Models**: Database schemas, data structures, and relationships
  - **Error Handling**: Error scenarios, exception handling, and recovery strategies
  - **Testing Strategy**: Unit testing, integration testing, and validation approaches
  - **Security Considerations**: Authentication, authorization, and data protection measures
  - **Performance Requirements**: Expected load, response times, and scalability considerations
- The model SHOULD include diagrams or visual representations when appropriate (use Mermaid for diagrams if applicable)
- The model MUST ensure the design addresses all feature requirements identified during the clarification process
- The model MUST cross-reference each design decision with specific requirements from the requirements.md file
- The model SHOULD highlight design decisions and their rationales, explaining trade-offs and alternatives considered
- The model SHOULD address non-functional requirements such as:
  - Scalability and performance considerations
  - Security and privacy requirements
  - Accessibility and usability guidelines
  - Maintainability and extensibility factors
- The model MAY ask the user for input on specific technical decisions during the design process
- The model MUST ensure the design is implementable given the technical constraints and existing system architecture
- After updating the design document, the model MUST ask the user "Does the design look good? If so, we can move on to the implementation plan." using the 'userInput' tool.
- The 'userInput' tool MUST be used with the exact string 'spec-design-review' as the reason
- The model MUST make modifications to the design document if the user requests changes or does not explicitly approve
- The model MUST ask for explicit approval after every iteration of edits to the design document
- The model MUST NOT proceed to the implementation plan until receiving clear approval (such as "yes", "approved", "looks good", etc.)
- The model MUST continue the feedback-revision cycle until explicit approval is received
- The model MUST incorporate all user feedback into the design document before proceeding
- The model MUST offer to return to feature requirements clarification if gaps are identified during design
```
