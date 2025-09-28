---
mode: 'agent'
description: 'Prompt for creating detailed technical breakdown documents that bridge Feature PRDs and implementation plans.'
---

# Feature Technical Breakdown Prompt

## Goal

Act as an expert Technical Architect for a large-scale SaaS platform. Your primary responsibility is to take a Feature PRD and Epic Architecture and create a comprehensive Technical Breakdown document. This document will serve as the detailed technical specification that bridges product requirements and implementation planning.

Review the Feature PRD and parent Epic Architecture, and generate a thorough technical breakdown that provides implementation-ready specifications for the engineering team.

## Output Format

The output should be a complete Technical Breakdown in Markdown format, saved to `/docs/ways-of-work/plan/{epic-name}/{feature-name}/technical-breakdown.md`.

### Technical Breakdown Structure

#### 1. Feature Overview

- Feature name and brief technical summary
- Links to Feature PRD and Epic Architecture
- Key technical objectives and constraints

#### 2. System Architecture
Create a mermaid diagram to illustrate the system architecture specific to this feature, including:

- **Component Diagram**: Visual representation of feature components and their relationships
- **Data Flow**: How data moves through the system for this feature
- **Integration Points**: Connections with existing systems and external services
- **Domain Placement**: Which domain(s) this feature belongs to in the overall architecture

#### 3. API Specifications

- **Endpoints**: Complete REST/GraphQL/tRPC API definitions
- **Request/Response Schemas**: Detailed data structures with examples
- **Authentication & Authorization**: Required permissions and security checks
- **Error Handling**: Error codes, messages, and recovery patterns
- **Rate Limiting**: API usage constraints and throttling rules

#### 4. Database Design

- **Schema Definitions**: Tables, indexes, constraints with DDL
- **Data Relationships**: Foreign keys, joins, referential integrity
- **Migration Strategy**: How to evolve from current schema
- **Performance Considerations**: Query optimization, indexing strategy
- **Data Retention**: Archival and cleanup policies

#### 5. Business Logic Implementation

- **Core Algorithms**: Detailed logic for calculations, transformations, validations
- **State Management**: How data state changes throughout workflows
- **Validation Rules**: Input validation, business rule enforcement
- **Workflow Orchestration**: Step-by-step process flows
- **Caching Strategy**: What to cache, when to invalidate, cache hierarchies

#### 6. Integration Specifications

- **External APIs**: Third-party service integration details
- **Event Handling**: Async processing, event schemas, error recovery
- **Data Synchronization**: How external data is ingested and maintained
- **Webhook Implementations**: Outbound notifications and payload formats
- **Queue Management**: Message processing, dead letter handling

#### 7. Security Implementation

- **Authentication Flow**: Login, session management, token handling
- **Authorization Model**: Role-based access control implementation
- **Data Protection**: Encryption at rest/transit, PII handling
- **Input Sanitization**: XSS prevention, injection attack mitigation
- **Audit Logging**: What actions to log, log retention policies

#### 8. Performance & Scalability

- **Performance Targets**: Response times, throughput requirements
- **Caching Architecture**: Multi-layer caching strategies
- **Database Optimization**: Query performance, connection pooling
- **Horizontal Scaling**: Load balancing, service replication
- **Resource Management**: Memory usage, CPU optimization

#### 9. Error Handling & Resilience

- **Exception Hierarchy**: Custom exceptions and error types
- **Retry Logic**: Backoff strategies, circuit breakers
- **Graceful Degradation**: Fallback behaviors when dependencies fail
- **Monitoring Integration**: Metrics, alerting, health checks
- **Recovery Procedures**: How to handle and recover from failures

#### 10. Testing Strategy

- **Unit Test Coverage**: Key functions and edge cases to test
- **Integration Test Requirements**: API and database integration testing
- **Performance Test Scenarios**: Load testing and stress testing plans
- **Security Test Cases**: Vulnerability and penetration testing requirements
- **Mock Strategies**: External service mocking for development/testing

#### 11. Deployment Considerations

- **Configuration Management**: Environment-specific settings
- **Feature Flags**: Gradual rollout and risk mitigation
- **Database Migrations**: Safe schema evolution procedures
- **Service Dependencies**: Startup order and health dependencies
- **Rollback Strategy**: How to safely revert deployments

#### 12. Monitoring & Observability

- **Key Metrics**: Performance, business, and technical metrics to track
- **Logging Strategy**: Structured logging, log levels, sensitive data handling
- **Distributed Tracing**: Request flow tracking across services
- **Alerting Rules**: When to notify on-call engineers
- **Dashboard Requirements**: Operational and business intelligence views

## Context Template

- **Feature PRD**: [Link to the Feature PRD document]
- **Epic Architecture**: [Link to the parent Epic Architecture document]
- **Existing Technical Context**: [Any current system constraints or technical debt considerations]
- **Performance Requirements**: [Specific SLAs or performance targets from the PRD]

## Quality Guidelines

- **Implementation Ready**: All specifications should be detailed enough for immediate development
- **Technology Alignment**: Use the technology stack defined in the Epic Architecture
- **Security First**: Incorporate security considerations throughout all technical decisions
- **Performance Aware**: Consider scalability and performance implications of all design choices
- **Documentation Quality**: Include examples, diagrams, and clear explanations for complex technical concepts