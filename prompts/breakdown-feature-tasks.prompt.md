---
mode: 'agent'
description: 'Prompt for breaking down features into granular, actionable development tasks with dependencies and estimates.'
---

# Feature Tasks Breakdown Prompt

## Goal

Act as an expert Engineering Manager and Technical Lead for a large-scale SaaS platform. Your primary responsibility is to take a Feature PRD, Technical Breakdown, and Implementation Plan and create a comprehensive Tasks Breakdown document. This document will provide granular, actionable development tasks that can be directly converted into GitHub issues or project management tickets.

Review the Feature PRD, Technical Breakdown, and Implementation Plan, and generate a detailed task breakdown that enables efficient sprint planning and development execution. The Implementation Plan provides the detailed technical architecture, database schemas, API designs, and component hierarchies that should guide the task creation.

## Output Format

The output should be a complete Tasks Breakdown in Markdown format, saved to `/docs/ways-of-work/plan/{epic-name}/{feature-name}/tasks-breakdown.md`.

### Tasks Breakdown Structure

#### 1. Feature Summary

- Feature name and development scope overview
- Links to Feature PRD, Technical Breakdown, and Implementation Plan
- Total estimated effort and timeline summary
- Key development milestones

#### 2. Development Phases

Break the feature into logical development phases (typically 1-3 sprints each):

##### Phase Structure:
- **Phase Name & Objective**
- **Duration Estimate**
- **Key Deliverables**
- **Success Criteria**
- **Dependencies & Blockers**

#### 3. Detailed Task Breakdown

For each development phase, provide granular tasks:

##### Task Format:
```markdown
### [TASK-ID] Task Title
**Type**: [Backend/Frontend/DevOps/Testing/Documentation]
**Effort**: [T-Shirt Size: XS/S/M/L/XL] ([Story Points/Hours])
**Dependencies**: [List of prerequisite tasks]
**Assignee Suggestion**: [Role/Skills needed]

**Description**: 
Clear, actionable description of what needs to be built

**Acceptance Criteria**:
- [ ] Specific, testable criteria
- [ ] Performance requirements if applicable
- [ ] Security requirements if applicable

**Technical Notes**:
- Implementation approach
- Key technical decisions
- Files/components to modify

**Testing Requirements**:
- Unit test coverage expectations
- Integration test scenarios
- Manual testing steps

**Definition of Done**:
- [ ] Code written and reviewed
- [ ] Tests passing
- [ ] Documentation updated
- [ ] Deployed to staging
```

#### 4. Task Dependencies Matrix

Visual representation of task dependencies:

```markdown
| Task ID | Depends On | Blocks | Critical Path |
|---------|------------|--------|---------------|
| TASK-001 | - | TASK-002, TASK-003 | ✓ |
| TASK-002 | TASK-001 | TASK-004 | ✓ |
```

#### 5. Sprint Planning Suggestions

- **Sprint 1 Recommendations**: Which tasks to include in first sprint
- **Sprint 2 Recommendations**: Follow-up tasks and dependencies
- **Sprint 3+ Recommendations**: Remaining work and refinements
- **Risk Mitigation**: Parallel work opportunities and blockers

#### 6. Resource Requirements

- **Backend Developers**: Number needed, specific skills required
- **Frontend Developers**: Framework expertise, UI/UX collaboration needs
- **DevOps Engineers**: Infrastructure and deployment support
- **QA Engineers**: Testing strategy and automation needs
- **Design Resources**: UI/UX design requirements
- **Product Management**: Requirements clarification and stakeholder coordination

#### 7. Technical Debt & Refactoring Tasks

- **Code Quality Improvements**: Refactoring needed for feature implementation
- **Performance Optimizations**: Database queries, API optimizations
- **Security Enhancements**: Authentication, authorization improvements
- **Documentation Updates**: API docs, architectural documentation
- **Test Coverage Improvements**: Missing test scenarios

#### 8. Integration & Testing Tasks

- **API Integration Testing**: External service integration validation
- **End-to-End Testing**: User workflow testing scenarios
- **Performance Testing**: Load testing and benchmarking tasks
- **Security Testing**: Vulnerability assessment tasks
- **User Acceptance Testing**: Product owner validation scenarios

#### 9. DevOps & Deployment Tasks

- **Infrastructure Setup**: New services, databases, caching layers
- **CI/CD Pipeline Updates**: Build, test, and deployment automation
- **Configuration Management**: Environment variables, feature flags
- **Monitoring Setup**: Metrics, logging, alerting configuration
- **Documentation**: Deployment procedures, troubleshooting guides

#### 10. Risk Assessment & Mitigation

- **High-Risk Tasks**: Complex implementations with uncertainty
- **External Dependencies**: Third-party services, API limitations
- **Knowledge Gaps**: Learning curve for new technologies
- **Parallel Work Opportunities**: Tasks that can be developed simultaneously
- **Contingency Plans**: Alternative approaches for high-risk items

#### 11. Quality Gates & Checkpoints

- **Code Review Requirements**: Peer review process and standards
- **Architecture Review**: Technical design validation checkpoints
- **Security Review**: Security assessment requirements
- **Performance Review**: Performance benchmark validation
- **Product Review**: Feature acceptance and user experience validation

#### 12. Communication & Collaboration Plan

- **Stakeholder Updates**: When and how to communicate progress
- **Cross-Team Coordination**: Dependencies on other teams
- **Technical Decision Points**: When to escalate architectural decisions
- **User Feedback Integration**: Beta testing and feedback incorporation
- **Documentation Handoffs**: Knowledge transfer requirements

## Context Template

- **Feature PRD**: [Link to the Feature PRD document]
- **Technical Breakdown**: [Link to the Technical Breakdown document]
- **Implementation Plan**: [Link to the Implementation Plan document]
- **Team Composition**: [Current team size and skill sets]
- **Sprint Capacity**: [Available story points or development hours per sprint]
- **Timeline Constraints**: [Any fixed deadlines or milestone requirements]

## Quality Guidelines

- **Actionable Tasks**: Every task should be specific enough for immediate development work
- **Realistic Estimates**: Effort estimates should account for testing, code review, and documentation
- **Clear Dependencies**: Task relationships should be explicit and manageable
- **Testable Acceptance Criteria**: Each task should have verifiable completion criteria
- **Risk Awareness**: Identify and plan for potential blockers and uncertainties
- **Sprint-Sized Work**: Break large tasks into sprint-appropriate chunks (typically 1-8 story points)

## Estimation Guidelines

- **XS (1-2 hours)**: Simple configuration changes, minor bug fixes
- **S (0.5-1 day)**: Small feature additions, unit test creation
- **M (1-3 days)**: Standard feature implementation, API endpoint creation
- **L (3-5 days)**: Complex feature development, significant refactoring
- **XL (1-2 weeks)**: Major system integration, architectural changes

**Note**: Tasks larger than XL should be broken down into smaller, more manageable pieces.