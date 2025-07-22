# Specification Review and Validation

## Introduction
This workflow prompt performs comprehensive validation and quality assessment of specification documents within the RRI Development Prompts system. It validates EARS format compliance, checks traceability between requirements-design-tasks, identifies gaps, and generates actionable recommendations for specification improvement.

**Intent**: Ensure specification quality, completeness, and consistency before implementation begins.

**Context**: Use when reviewing existing specifications, validating new feature specifications, or conducting quality audits of specification repositories.

## Constraints and Guidelines

### Input Requirements
- **MANDATORY**: Provide the feature specification directory path (e.g., `.github/specs/feature-name/`)
- **OPTIONAL**: Validation scope (full-comprehensive, requirements-only, traceability-focus, ears-compliance)
- **OPTIONAL**: Output format preference (detailed-report, summary-only, checklist-format)
- **OPTIONAL**: Integration with existing validation tools or CI/CD systems

### Processing Constraints
1. **Scope Boundary**: Only analyze files within the specified feature specification directory
2. **File Type Limitation**: Focus on `.md` files following the standard spec structure (requirements.md, design.md, tasks.md)
3. **EARS Format Enforcement**: All acceptance criteria must follow EARS syntax patterns
4. **Traceability Requirement**: Every requirement must be addressed in design; every design element must be implemented in tasks
5. **Gap Detection**: Identify and report all missing linkages, orphaned elements, and incomplete sections

### Output Constraints
1. **Structured Format**: Generate validation results using consistent schema with actionable recommendations
2. **Severity Levels**: Classify issues as Critical, Major, Minor, or Informational
3. **Specificity Requirement**: Provide exact line numbers, section references, and suggested fixes
4. **Actionability**: Every identified issue must include specific steps for resolution
5. **Completeness Score**: Calculate and report overall specification quality percentage

## Validation Process

### Phase 1: File Structure and Completeness Analysis

**Analyze specification directory structure:**
1. Verify presence of required files (requirements.md, design.md, tasks.md)
2. Check for optional files (additional documentation, diagrams, references)
3. Validate file naming conventions and directory organization
4. Assess specification completeness percentage based on file presence

**Output Requirements:**
- File inventory with status (present/missing/malformed)
- Completeness percentage calculation
- Missing file recommendations with templates

### Phase 2: Requirements Document Validation

**EARS Format Compliance Analysis:**
1. Extract all acceptance criteria from requirements.md
2. Validate each criterion against EARS syntax patterns:
   - WHEN [trigger condition], THE SYSTEM SHALL [system response]
   - IF [condition], THEN THE SYSTEM SHALL [response]
   - THE SYSTEM SHALL [mandatory behavior]
   - WHILE [state condition], THE SYSTEM SHALL [continuous behavior]
3. Identify non-compliant criteria and suggest EARS-compliant alternatives
4. Check for completeness of scenarios (happy path, error cases, edge conditions)

**User Story Quality Assessment:**
1. Validate user story format: "As a [user type], I want [functionality], so that [benefit]"
2. Check for clear user types, specific functionality descriptions, and measurable benefits
3. Verify alignment between user stories and acceptance criteria
4. Identify missing or vague user stories

**Requirements Traceability Setup:**
1. Extract and catalog all requirements with unique identifiers
2. Create requirement reference database for cross-document analysis
3. Validate requirement numbering and organization consistency
4. Check for requirement interdependencies and conflicts

**Output Requirements:**
- EARS compliance report with specific syntax errors and corrections
- User story quality assessment with improvement recommendations
- Requirements catalog with traceability preparation
- Severity-classified issues list with line number references

### Phase 3: Design Document Validation

**Architecture and Design Analysis:**
1. Verify design addresses all requirements from requirements.md
2. Check for design completeness (architecture, components, interfaces, data models)
3. Validate design consistency and feasibility
4. Identify over-design or under-design relative to requirements

**Requirement-Design Traceability:**
1. Map each requirement to corresponding design elements
2. Identify orphaned design elements not linked to requirements
3. Find requirements without design coverage
4. Validate design decisions justify requirement fulfillment

**Technical Consistency Review:**
1. Check for consistent terminology and naming conventions
2. Verify interface definitions and component interactions
3. Validate data model consistency with requirements
4. Assess design scalability and maintainability considerations

**Output Requirements:**
- Requirement-to-design traceability matrix
- Design completeness assessment with gap identification
- Technical consistency report with specific recommendations
- Design quality score with improvement areas

### Phase 4: Implementation Tasks Validation

**Task Coverage Analysis:**
1. Verify all design elements are covered by implementation tasks
2. Check task granularity and estimated effort appropriateness
3. Validate task dependencies and sequencing logic
4. Identify missing tasks for complete feature implementation

**Task-Requirement Linkage Validation:**
1. Ensure each task references specific requirements it addresses
2. Verify task outcomes will satisfy acceptance criteria
3. Check for task scope alignment with requirement complexity
4. Identify orphaned tasks not linked to requirements or design

**Implementation Feasibility Assessment:**
1. Evaluate task breakdown sufficiency for development execution
2. Check for realistic effort estimates and timeline considerations
3. Validate testing strategy inclusion in task definitions
4. Assess risk mitigation and error handling coverage

**Output Requirements:**
- Task coverage matrix showing requirement-design-task linkages
- Implementation feasibility report with risk assessment
- Missing task identification with suggested additions
- Task quality score with specific improvement recommendations

### Phase 5: Cross-Document Consistency Analysis

**Inter-Document Traceability Validation:**
1. Generate complete traceability matrix: Requirements → Design → Tasks
2. Identify and report all broken linkages and orphaned elements
3. Verify consistency of terminology and concepts across documents
4. Check for conflicting statements or contradictory specifications

**Completeness Gap Analysis:**
1. Identify requirements without design coverage
2. Find design elements without implementation tasks
3. Locate acceptance criteria without corresponding test coverage
4. Report missing specification sections or incomplete documentation

**Quality Metrics Calculation:**
1. Calculate overall specification completeness percentage
2. Compute EARS compliance rate for acceptance criteria
3. Determine traceability coverage percentage
4. Generate quality trend analysis if historical data available

**Output Requirements:**
- Complete traceability matrix with visual gap identification
- Comprehensive gap analysis report with prioritized fixes
- Quality metrics dashboard with trend analysis
- Executive summary with overall specification assessment

## Validation Output Schema

### Validation Report Structure
```json
{
  "specification_id": "feature-name",
  "validation_timestamp": "2025-07-22T10:30:00Z",
  "overall_quality_score": 85.5,
  "validation_scope": "full-comprehensive",
  
  "file_structure_analysis": {
    "completeness_percentage": 100.0,
    "files_present": ["requirements.md", "design.md", "tasks.md"],
    "files_missing": [],
    "issues": []
  },
  
  "requirements_validation": {
    "ears_compliance_rate": 92.3,
    "user_story_quality_score": 88.0,
    "total_requirements": 15,
    "compliant_criteria": 12,
    "issues": [
      {
        "severity": "Major",
        "category": "EARS Compliance",
        "location": "requirements.md:line 45",
        "description": "Acceptance criterion lacks proper EARS format",
        "current_text": "System should validate user input",
        "suggested_fix": "THE SYSTEM SHALL validate user input format WHEN user submits form data",
        "impact": "Ambiguous requirement may lead to implementation inconsistencies"
      }
    ]
  },
  
  "design_validation": {
    "requirement_coverage_percentage": 95.2,
    "design_completeness_score": 87.5,
    "consistency_score": 91.0,
    "issues": [
      {
        "severity": "Minor",
        "category": "Traceability",
        "location": "design.md:Architecture section",
        "description": "Requirement 3.2 not explicitly addressed in design",
        "suggested_fix": "Add authentication component specification to address requirement 3.2",
        "impact": "Missing design coverage for security requirement"
      }
    ]
  },
  
  "task_validation": {
    "implementation_coverage_percentage": 89.7,
    "task_quality_score": 83.5,
    "feasibility_assessment": "Good",
    "issues": [
      {
        "severity": "Critical",
        "category": "Implementation Coverage",
        "location": "tasks.md:Task 2.3",
        "description": "No tasks address requirement 4.1 (error handling)",
        "suggested_fix": "Add task: 'Implement comprehensive error handling for user input validation'",
        "impact": "Critical requirement will not be implemented"
      }
    ]
  },
  
  "traceability_analysis": {
    "overall_traceability_percentage": 91.3,
    "requirements_to_design": 95.2,
    "design_to_tasks": 89.7,
    "end_to_end_coverage": 87.5,
    "broken_linkages": 3,
    "orphaned_elements": 2
  },
  
  "recommendations": {
    "critical_actions": [
      "Add implementation tasks for requirement 4.1",
      "Fix EARS format for 3 non-compliant acceptance criteria"
    ],
    "improvement_opportunities": [
      "Enhance design detail for user interface components",
      "Add more specific testing criteria to task definitions"
    ],
    "quality_targets": {
      "ears_compliance": "Achieve 95%+ compliance",
      "traceability_coverage": "Achieve 95%+ end-to-end traceability",
      "overall_quality": "Target 90%+ overall quality score"
    }
  }
}
```

### Severity Classification Guidelines

**Critical Issues** (Block implementation):
- Missing requirements for core functionality
- Broken traceability preventing implementation
- Non-testable acceptance criteria
- Conflicting requirements or design decisions

**Major Issues** (Impact quality/timeline):
- Poor EARS format compliance affecting clarity
- Incomplete design coverage for requirements
- Missing implementation tasks for design elements
- Insufficient error handling or edge case coverage

**Minor Issues** (Improvement opportunities):
- Formatting inconsistencies
- Minor terminology variations
- Optional documentation enhancements
- Style guide compliance items

**Informational** (Best practice suggestions):
- Additional testing strategies
- Performance optimization opportunities
- Maintainability improvements
- Documentation enhancement suggestions

## Usage Examples

### Example 1: Comprehensive Validation
**Input**: Full specification validation for user authentication feature
**Scope**: full-comprehensive
**Output**: Complete validation report with all issues, traceability matrix, and improvement recommendations

### Example 2: EARS Compliance Focus
**Input**: Requirements-only validation for API specification
**Scope**: requirements-only, ears-compliance
**Output**: EARS format analysis with specific syntax corrections and compliance percentage

### Example 3: Traceability Audit
**Input**: Multi-feature project with cross-dependencies
**Scope**: traceability-focus
**Output**: Cross-document linkage analysis, gap identification, and coverage reporting

### Example 4: Quick Quality Check
**Input**: Pre-implementation validation gate
**Scope**: summary-only
**Output**: Executive summary with pass/fail status and critical blocking issues only

## Integration Points

### Workflow Integration
- **Trigger**: After specification creation or modification
- **Dependencies**: Requires shared utilities (EARS validation, file parsing)
- **Output Integration**: Feeds validation results to testing strategy and implementation planning
- **Hook Integration**: Automated validation gates in specification workflow

### Tool Compatibility
- **VS Code Extension**: Integrate with workspace validation commands
- **CI/CD Integration**: Automated validation in pull request workflows
- **Documentation Tools**: Export validation reports to project documentation
- **Metrics Dashboard**: Feed quality metrics to project health monitoring

### Error Recovery
- **Malformed Files**: Graceful handling with partial validation and specific error reporting
- **Missing Dependencies**: Continue validation with warnings for missing shared utilities
- **Large Specifications**: Chunked processing with progress reporting for large feature sets
- **Network Issues**: Local-only validation with optional remote tool integration

This prompt provides comprehensive specification validation with actionable feedback to ensure quality before implementation begins.
