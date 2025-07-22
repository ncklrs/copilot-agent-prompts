# Enhanced Prompt Selector System

## Overview
This system provides selective inclusion of enhanced workflow prompts through chat flags/commands. Use these commands to include specific enhanced capabilities in your development workflow while maintaining access to core prompts.

## Usage Commands

### Selective Inclusion by Category

#### `/validation` - Include Validation & Testing Prompts
```
#enhanced-validation
```
**Includes:**
- `prompts/enhanced/validation/review-validation.md` - EARS-compliant specification review
- `prompts/enhanced/validation/testing-strategy.md` - Comprehensive testing strategy generation

#### `/coordination` - Include Cross-Feature Coordination
```
#enhanced-coordination
```
**Includes:**
- `prompts/enhanced/coordination/cross-feature-integration.md` - Cross-feature integration analysis
- `prompts/enhanced/coordination/evolution-management.md` - Change impact assessment

#### `/analysis` - Include Analysis & Assessment
```
#enhanced-analysis
```
**Includes:**
- `prompts/enhanced/analysis/performance-security.md` - Performance and security analysis
- `prompts/enhanced/analysis/technical-debt.md` - Technical debt assessment

#### `/documentation` - Include Documentation Generation
```
#enhanced-documentation
```
**Includes:**
- `prompts/enhanced/documentation/documentation-generation.md` - Multi-format documentation generation

#### `/process` - Include Process Improvement
```
#enhanced-process
```
**Includes:**
- `prompts/enhanced/process/process-retrospective.md` - Process retrospective and improvement

### Combined Usage

#### `/enhanced-all` - Include All Enhanced Prompts
```
#enhanced-all
```
**Includes:** All 8 enhanced workflow prompts for comprehensive development support

#### `/enhanced-dev` - Developer-Focused Prompts
```
#enhanced-dev
```
**Includes:**
- Validation & Testing
- Analysis & Assessment
- Technical Debt

#### `/enhanced-pm` - Project Management Focused
```
#enhanced-pm
```
**Includes:**
- Cross-Feature Coordination
- Evolution Management
- Process Retrospective

#### `/enhanced-docs` - Documentation Focused
```
#enhanced-docs
```
**Includes:**
- Documentation Generation
- Process Retrospective

## Implementation Guide

### In Chat Usage
Simply include the desired flag(s) in your chat message:

```
I need to review this specification #enhanced-validation
```

```
Let's analyze the performance implications /analysis and generate documentation /documentation
```

```
Full development workflow review needed #enhanced-all
```

### Prompt Chaining
Combine multiple categories for comprehensive workflows:

```
Starting new feature development:
/validation /coordination /analysis
```

```
Pre-release checklist:
/enhanced-dev /documentation /process
```

## File Organization

### Core Prompts (Always Available)
Located in `.github/prompts/core/` - These are always included in the base workflow:
- Core specification-driven development prompts
- Basic workflow templates
- Standard development guidelines

### Enhanced Prompts (Selective)
Located in `.github/prompts/enhanced/` - Include via flags:
- Advanced validation and testing strategies
- Cross-feature coordination and integration
- Performance, security, and technical debt analysis
- Multi-format documentation generation
- Process improvement and retrospectives

## Configuration

### Adding New Enhanced Prompts
1. Create new prompt file in `.github/prompts/enhanced/[category]/`
2. Add corresponding flag/command to this selector
3. Update category mappings as needed

### Customizing Categories
Modify the category mappings above to match your team's workflow preferences and organizational needs.

## Examples

### Feature Development Workflow
```
Starting new user authentication feature:
/validation /coordination /analysis

This will include:
- Specification review and validation
- Cross-feature integration analysis  
- Performance and security assessment
- Technical debt evaluation
```

### Documentation Sprint
```
Updating project documentation:
/documentation /process

This will include:
- Multi-format documentation generation
- Process retrospective for documentation improvements
```

### Release Preparation
```
Preparing v2.0 release:
#enhanced-all

This includes comprehensive review across all enhanced capabilities
```

## Benefits

1. **Selective Inclusion**: Only include enhanced capabilities when needed
2. **Clean Separation**: Core prompts remain easily accessible
3. **Flexible Workflows**: Mix and match enhanced capabilities
4. **Team Customization**: Different flags for different roles/workflows
5. **Scalable System**: Easy to add new enhanced prompts and categories

## Next Steps

1. Test the flag system with your development workflows
2. Customize categories based on team needs
3. Add new enhanced prompts as workflows evolve
4. Integrate with team documentation and onboarding processes
