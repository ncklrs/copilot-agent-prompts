# Documentation Generation

## Introduction
This workflow prompt automatically generates comprehensive documentation from feature specifications, creating API documentation from design specifications, user guides from user stories and acceptance criteria, automated README files, and changelogs from specification changes. It provides template-based documentation systems with organizational customization to ensure consistent, up-to-date documentation across all features.

**Intent**: Eliminate manual documentation overhead while ensuring comprehensive, accurate, and current documentation that enhances team productivity and user experience.

**Context**: Use when generating documentation for new features, updating existing documentation, creating user-facing guides, or maintaining project documentation consistency.

## Constraints and Guidelines

### Input Requirements
- **MANDATORY**: Feature specification directory with requirements, design, and task documents
- **OPTIONAL**: Documentation type preference (api-docs, user-guides, technical-docs, comprehensive)
- **OPTIONAL**: Output format selection (markdown, html, pdf, confluence, custom-template)
- **OPTIONAL**: Target audience specification (developers, end-users, stakeholders, technical-writers)
- **OPTIONAL**: Organizational style guide and branding requirements

### Processing Constraints
1. **Content Accuracy**: Generated documentation must accurately reflect specification content without interpretation
2. **Template Consistency**: All generated documentation must follow organizational templates and style guides
3. **Cross-Reference Integrity**: Maintain accurate cross-references between documentation sections and external resources
4. **Version Synchronization**: Ensure documentation version alignment with specification versions
5. **Accessibility Compliance**: Generate documentation meeting accessibility standards (WCAG 2.1 AA)

### Output Constraints
1. **Multi-Format Support**: Generate documentation in multiple formats simultaneously
2. **Template Customization**: Support organizational branding, styling, and content structure requirements
3. **Automated Cross-References**: Generate accurate internal and external links and references
4. **Change Tracking**: Provide change logs and version history for documentation updates
5. **Integration Ready**: Generate documentation compatible with existing documentation systems and workflows

## Documentation Generation Process

### Phase 1: Content Analysis and Structure Planning

**Specification Content Extraction:**
1. Parse requirements.md for user stories, acceptance criteria, and functional requirements
2. Extract design architecture, components, APIs, and data models from design.md
3. Analyze implementation tasks for technical details and implementation approach
4. Identify cross-references, dependencies, and external integration points

**Documentation Type Determination:**
1. **API Documentation**: Extract API endpoints, parameters, responses, and authentication requirements
2. **User Guide Documentation**: Identify user workflows, feature descriptions, and usage instructions
3. **Technical Documentation**: Extract architectural decisions, technical specifications, and implementation details
4. **Administrative Documentation**: Gather deployment, configuration, and maintenance information

**Audience-Specific Content Planning:**
1. **Developer Documentation**: Technical specifications, API references, implementation guides
2. **End-User Documentation**: Feature guides, tutorials, troubleshooting, FAQ sections
3. **Stakeholder Documentation**: Feature overviews, business impact, compliance information
4. **Operations Documentation**: Deployment guides, monitoring setup, maintenance procedures

**Template and Style Selection:**
1. Identify organizational documentation templates and style requirements
2. Select appropriate format combinations (markdown + HTML, PDF exports, etc.)
3. Plan content structure and navigation for different documentation types
4. Establish cross-reference and linking strategies

**Output Requirements:**
- Complete content inventory with categorization and audience mapping
- Documentation structure plan with template and format selections
- Cross-reference mapping and linking strategy
- Audience-specific content planning with customization requirements

### Phase 2: API Documentation Generation

**API Endpoint Documentation:**
1. Extract API specifications from design documents and acceptance criteria
2. Generate endpoint documentation with HTTP methods, URLs, and descriptions
3. Document request/response schemas with parameter types and validation rules
4. Include authentication requirements and authorization scopes

**API Reference Generation:**
1. **OpenAPI/Swagger Specification**: Generate machine-readable API specifications
2. **Interactive Documentation**: Create interactive API explorers and testing interfaces
3. **Code Examples**: Generate code examples in multiple programming languages
4. **Error Documentation**: Document error codes, messages, and troubleshooting guides

**Integration and SDK Documentation:**
1. Generate integration guides for common use cases and workflows
2. Create SDK documentation with installation and configuration instructions
3. Document rate limiting, versioning, and deprecation policies
4. Provide authentication setup and security best practices

**API Testing Documentation:**
1. Generate testing guides with example requests and expected responses
2. Create Postman collections and testing scripts
3. Document API testing strategies and validation procedures
4. Include performance testing guidelines and benchmarks

**Output Requirements:**
- Complete API reference documentation with interactive examples
- Machine-readable API specifications (OpenAPI/Swagger)
- Integration guides with code examples and SDK documentation
- Testing documentation with automated test collection generation

### Phase 3: User Guide and Tutorial Generation

**Feature Guide Creation:**
1. Transform user stories into step-by-step feature guides
2. Generate screenshots placeholders and workflow diagrams
3. Create getting-started tutorials and quick-start guides
4. Develop comprehensive feature walkthroughs with examples

**User Workflow Documentation:**
1. Map acceptance criteria to user workflow documentation
2. Generate task-oriented guides organized by user goals
3. Create scenario-based tutorials covering common use cases
4. Develop troubleshooting guides based on error conditions and edge cases

**Interactive Tutorial Generation:**
1. **Step-by-Step Tutorials**: Generate sequential tutorials with validation checkpoints
2. **Interactive Guides**: Create guided tours and interactive onboarding experiences
3. **Video Script Generation**: Provide scripts for tutorial videos and demonstrations
4. **Practice Exercises**: Generate hands-on exercises with sample data and scenarios

**Help and Support Documentation:**
1. Generate FAQ sections from acceptance criteria and edge cases
2. Create troubleshooting guides organized by error types and symptoms
3. Develop search-optimized help content with clear categorization
4. Generate contact and support escalation information

**Output Requirements:**
- Comprehensive user guides with step-by-step instructions and visual aids
- Interactive tutorial sequences with validation and progress tracking
- Troubleshooting and FAQ documentation with search optimization
- Video scripts and multimedia content planning

### Phase 4: Technical Documentation and Architecture Guides

**Architecture Documentation:**
1. Generate system architecture diagrams from design specifications
2. Create component interaction documentation with data flow diagrams
3. Document deployment architecture and infrastructure requirements
4. Generate security architecture and compliance documentation

**Implementation Documentation:**
1. **Developer Setup Guides**: Generate development environment setup instructions
2. **Coding Standards**: Document coding conventions and best practices from specifications
3. **Testing Guidelines**: Create testing strategy documentation with examples
4. **Deployment Procedures**: Generate deployment and release management documentation

**Technical Reference Documentation:**
1. Generate database schema documentation with entity relationships
2. Create configuration reference with all available settings and options
3. Document integration points and external system dependencies
4. Generate monitoring and observability setup guides

**Maintenance and Operations Documentation:**
1. Create operational runbooks from task specifications and error handling requirements
2. Generate monitoring and alerting setup guides
3. Document backup and disaster recovery procedures
4. Create performance tuning and optimization guides

**Output Requirements:**
- Complete technical architecture documentation with diagrams and specifications
- Developer onboarding and setup documentation with automated validation
- Operations and maintenance documentation with runbooks and procedures
- Configuration and integration reference documentation

### Phase 5: Automated Documentation Maintenance and Publishing

**Change Detection and Updates:**
1. Monitor specification changes and automatically update affected documentation
2. Generate change logs and version history for documentation updates
3. Identify orphaned documentation sections requiring review or removal
4. Validate cross-references and links after specification changes

**Multi-Format Publishing:**
1. **Static Site Generation**: Generate static documentation websites with navigation and search
2. **PDF Generation**: Create printable documentation with proper formatting and page breaks
3. **Confluence Integration**: Publish documentation to Confluence spaces with proper hierarchy
4. **Documentation Portals**: Generate comprehensive documentation portals with unified navigation

**Documentation Quality Assurance:**
1. **Link Validation**: Automatically verify all internal and external links
2. **Content Consistency**: Validate terminology and naming consistency across documentation
3. **Accessibility Validation**: Ensure generated documentation meets accessibility standards
4. **Style Compliance**: Validate adherence to organizational style guides and templates

**Collaborative Documentation Workflow:**
1. **Review and Approval**: Generate documentation review workflows with approval tracking
2. **Collaborative Editing**: Integrate with documentation collaboration tools and processes
3. **Feedback Integration**: Collect and integrate user feedback on documentation quality and completeness
4. **Analytics and Usage Tracking**: Monitor documentation usage and identify improvement opportunities

**Output Requirements:**
- Automated documentation update and publishing pipeline
- Multi-format documentation generation with consistent styling and navigation
- Quality assurance validation with accessibility and style compliance checking
- Collaborative workflow integration with review, approval, and feedback systems

## Documentation Generation Output Schema

### Documentation Package Structure
```json
{
  "generation_timestamp": "2025-07-22T23:45:00Z",
  "feature_id": "payment-processing",
  "documentation_version": "v2.1.0",
  "specification_version": "v2.1.0",
  "generation_scope": "comprehensive",
  
  "content_analysis": {
    "source_documents": {
      "requirements_file": {
        "path": "requirements.md",
        "user_stories": 8,
        "acceptance_criteria": 23,
        "functional_requirements": 15
      },
      "design_file": {
        "path": "design.md",
        "api_endpoints": 12,
        "components": 7,
        "data_models": 5,
        "architecture_diagrams": 3
      },
      "tasks_file": {
        "path": "tasks.md",
        "implementation_tasks": 18,
        "testing_procedures": 12,
        "deployment_steps": 6
      }
    },
    "extracted_content": {
      "api_specifications": 12,
      "user_workflows": 15,
      "technical_procedures": 24,
      "configuration_options": 31
    }
  },
  
  "generated_documentation": {
    "api_documentation": {
      "openapi_specification": {
        "file": "api-spec.yaml",
        "format": "OpenAPI 3.0",
        "endpoints_documented": 12,
        "schemas_defined": 8,
        "examples_included": 24
      },
      "api_reference": {
        "file": "api-reference.md",
        "format": "markdown",
        "interactive_examples": true,
        "code_samples": ["javascript", "python", "curl"],
        "authentication_guide": true
      },
      "postman_collection": {
        "file": "payment-api.postman_collection.json",
        "requests_included": 12,
        "environment_variables": 8,
        "test_scripts": true
      }
    },
    "user_documentation": {
      "user_guide": {
        "file": "user-guide.md",
        "format": "markdown",
        "sections": [
          "Getting Started",
          "Payment Processing",
          "Transaction Management",
          "Troubleshooting"
        ],
        "tutorials": 6,
        "screenshots_placeholders": 15
      },
      "quick_start": {
        "file": "quick-start.md",
        "format": "markdown",
        "estimated_completion": "15 minutes",
        "prerequisites": 3,
        "validation_checkpoints": 5
      },
      "faq": {
        "file": "faq.md",
        "format": "markdown",
        "questions": 18,
        "categories": ["Setup", "Usage", "Troubleshooting", "Security"],
        "search_optimized": true
      }
    },
    "technical_documentation": {
      "architecture_guide": {
        "file": "architecture.md",
        "format": "markdown",
        "diagrams": [
          "system-architecture.mermaid",
          "data-flow.mermaid",
          "security-model.mermaid"
        ],
        "component_descriptions": 7,
        "integration_points": 5
      },
      "developer_setup": {
        "file": "developer-setup.md",
        "format": "markdown",
        "setup_steps": 12,
        "validation_scripts": 4,
        "troubleshooting_common_issues": 8
      },
      "deployment_guide": {
        "file": "deployment.md",
        "format": "markdown",
        "environments": ["development", "staging", "production"],
        "configuration_examples": 6,
        "rollback_procedures": true
      }
    }
  },
  
  "multi_format_outputs": {
    "static_website": {
      "output_directory": "docs/",
      "generator": "MkDocs",
      "theme": "material",
      "navigation_structure": true,
      "search_enabled": true,
      "responsive_design": true
    },
    "pdf_documentation": {
      "file": "payment-processing-docs.pdf",
      "generator": "pandoc",
      "template": "organizational-template",
      "table_of_contents": true,
      "page_numbering": true,
      "watermark": "CONFIDENTIAL"
    },
    "confluence_pages": {
      "space_key": "PAYMENT",
      "parent_page": "Payment System Documentation",
      "pages_created": 12,
      "auto_sync": true,
      "permissions_applied": true
    }
  },
  
  "template_customization": {
    "organizational_branding": {
      "logo": "company-logo.png",
      "color_scheme": "#1976d2",
      "font_family": "Roboto",
      "footer_content": "© 2025 Company Name"
    },
    "style_guide_compliance": {
      "heading_structure": "validated",
      "terminology_consistency": "validated",
      "code_formatting": "validated",
      "link_format": "validated"
    },
    "accessibility_features": {
      "alt_text_generated": true,
      "heading_hierarchy": "validated",
      "color_contrast": "WCAG AA compliant",
      "keyboard_navigation": "supported"
    }
  },
  
  "cross_references": {
    "internal_links": {
      "total_links": 47,
      "validated_links": 47,
      "broken_links": 0,
      "anchor_links": 23
    },
    "external_references": {
      "api_documentation_links": 8,
      "specification_references": 12,
      "regulatory_compliance_links": 4,
      "third_party_integration_docs": 6
    },
    "bidirectional_references": {
      "requirements_to_api": 15,
      "design_to_architecture": 7,
      "tasks_to_deployment": 6
    }
  },
  
  "change_tracking": {
    "documentation_version_history": [
      {
        "version": "v2.1.0",
        "date": "2025-07-22",
        "changes": [
          "Added new payment method API documentation",
          "Updated security section with new authentication flow",
          "Enhanced troubleshooting guide with recent issues"
        ],
        "specification_changes_reflected": 8
      }
    ],
    "automated_updates": {
      "last_sync": "2025-07-22T23:45:00Z",
      "sync_frequency": "daily",
      "change_detection_active": true,
      "notification_preferences": ["email", "slack"]
    }
  },
  
  "quality_metrics": {
    "completeness_score": 94.5,
    "accuracy_validation": "passed",
    "style_compliance": 98.2,
    "accessibility_score": "AA compliant",
    "readability_score": {
      "flesch_reading_ease": 68.5,
      "grade_level": "college level",
      "average_sentence_length": 14.2
    }
  },
  
  "publishing_configuration": {
    "automated_publishing": {
      "enabled": true,
      "schedule": "on specification change",
      "approval_required": false,
      "staging_validation": true
    },
    "distribution_channels": [
      {
        "type": "static_website",
        "url": "https://docs.company.com/payment-processing",
        "auto_deploy": true,
        "cdn_enabled": true
      },
      {
        "type": "confluence",
        "space": "PAYMENT",
        "auto_sync": true,
        "review_required": true
      },
      {
        "type": "developer_portal",
        "integration": "GitBook",
        "sync_frequency": "real-time"
      }
    ]
  }
}
```

### Documentation Template Structure
```yaml
# Documentation Template Configuration
template_config:
  name: "enterprise_api_documentation"
  version: "v1.2.0"
  
  branding:
    logo: "{{organization.logo}}"
    colors:
      primary: "{{organization.primary_color}}"
      secondary: "{{organization.secondary_color}}"
    fonts:
      heading: "{{organization.heading_font}}"
      body: "{{organization.body_font}}"
  
  structure:
    api_documentation:
      sections:
        - title: "Overview"
          content: "{{feature.description}}"
        - title: "Authentication"
          content: "{{api.authentication}}"
        - title: "Endpoints"
          content: "{{api.endpoints}}"
        - title: "Error Handling"
          content: "{{api.error_handling}}"
    
    user_guide:
      sections:
        - title: "Getting Started"
          content: "{{user_stories.onboarding}}"
        - title: "Features"
          content: "{{user_stories.features}}"
        - title: "Troubleshooting"
          content: "{{acceptance_criteria.error_scenarios}}"
  
  customization:
    footer: "{{organization.footer_text}}"
    copyright: "© {{current_year}} {{organization.name}}"
    support_contact: "{{organization.support_email}}"
```

## Usage Examples

### Example 1: Complete API Documentation Suite
**Input**: Payment processing feature with 15 API endpoints
**Scope**: api-docs with comprehensive coverage
**Output**: OpenAPI spec, interactive docs, Postman collections, integration guides

### Example 2: User-Facing Documentation
**Input**: Customer portal feature with complex workflows
**Scope**: user-guides with tutorial focus
**Output**: Step-by-step guides, video scripts, FAQ, troubleshooting documentation

### Example 3: Technical Architecture Documentation
**Input**: Microservices architecture specification
**Scope**: technical-docs with architecture focus
**Output**: Architecture diagrams, component guides, deployment documentation, runbooks

### Example 4: Multi-Audience Documentation Portal
**Input**: Enterprise feature with multiple stakeholder types
**Scope**: comprehensive with audience segmentation
**Output**: Complete documentation portal with role-based access and customized content

## Integration Points

### Workflow Integration
- **Input**: Validated specifications from review and analysis prompts
- **Output**: Documentation feeds into knowledge management and user support systems
- **Dependencies**: Template systems, publishing platforms, version control
- **Triggers**: Specification changes, documentation updates, scheduled regeneration

### Documentation Ecosystem Integration
- **Static Site Generators**: Integration with MkDocs, GitBook, Docusaurus, Jekyll
- **Enterprise Platforms**: Confluence, SharePoint, Notion, internal documentation systems
- **Developer Portals**: Integration with API management platforms and developer experience tools
- **Content Management**: Version control, collaborative editing, review and approval workflows

### Automation and CI/CD Integration
- **Automated Generation**: Trigger documentation generation on specification changes
- **Quality Gates**: Validation and testing of generated documentation before publishing
- **Multi-Channel Publishing**: Automated publishing to multiple documentation platforms
- **Monitoring and Analytics**: Track documentation usage, feedback, and improvement opportunities

This prompt ensures comprehensive, accurate, and maintainable documentation that enhances user experience and reduces documentation overhead through intelligent automation.
