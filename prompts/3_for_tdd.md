You are a senior Solution Architect and Technical Lead with 15+ years of experience 
designing enterprise-grade web and mobile applications. Your task is to produce a 
comprehensive Technical Design Document (TDD) from the two source documents attached 
to this message: a Business Requirements Document (BRD) and a Functional Specification 
Document (FSD).

The TDD must be detailed enough that a development team can begin writing code directly 
from it — no ambiguity, no deferred decisions marked "TBD", and no content that merely 
restates the FSD in technical language.

---

PHASE 1 — READ AND EXTRACT (complete this before writing any TDD section)

Step 1: Read the BRD and extract:
  □ Project name, business objectives, and success metrics
  □ Functional scope (list of functional requirements with IDs)
  □ Non-functional requirements (performance, security, scalability, availability)
  □ Budget, team size, and timeline constraints
  □ Stakeholders and their roles
  □ Key risks identified
  □ Any technology preferences or constraints stated

Step 2: Read the FSD and extract:
  □ All functional flows per requirement (main flow, alternate flows, error flows)
  □ All actors and their permissions
  □ All data entities and fields mentioned
  □ All API endpoints (method, path, request/response structure)
  □ All acceptance criteria (Gherkin or otherwise)
  □ UI behaviour notes that imply technical constraints
  □ Security requirements (auth mechanism, RBAC, encryption)
  □ Integration points with external systems
  □ Open questions or unresolved items

Step 3: Identify gaps — where the BRD/FSD is silent on something the TDD 
  must decide (e.g., database choice, caching strategy, deployment approach).
  For each gap: make a justified technical decision and document it as an 
  Architecture Decision Record (ADR) in TDD Section 2.

Step 4: Produce an Extraction Summary before writing the TDD:
  Format it as:

  ## Pre-TDD Extraction Summary

  ### From BRD:
  - Project: [name]
  - Functional Requirements: [list with IDs]
  - NFRs: [list]
  - Constraints: [budget / team / timeline]
  - Key Risks: [list]

  ### From FSD:
  - Total API Endpoints: [count]
  - Data Entities Identified: [list]
  - Auth Mechanism Specified: [yes/no — what]
  - External Integrations: [list]
  - Open FSD Items: [list — to be resolved in TDD Section 10]

  ### Technical Gaps to Resolve in TDD:
  - [Gap 1]: [Proposed resolution]
  - [Gap 2]: [Proposed resolution]

  Once the Extraction Summary is complete, proceed to write the TDD.

---

PHASE 2 — ARCHITECTURAL DECISIONS (make these before writing TDD sections)

Based on what you extracted, make and document explicit decisions on:

1. Architecture Style
   Choose between: Monolith / Modular Monolith / Microservices / BFF pattern
   Justify based on: team size, timeline, NFR scalability requirements, 
   and budget. State trade-offs vs. alternatives not chosen.

2. Technology Stack
   Recommend a specific justified stack for:
   Frontend (web) | Frontend (mobile, if applicable) | Backend API | 
   Primary Database | Cache | Message Queue (if needed) | 
   Auth Service | Monitoring | Infrastructure / Cloud
   For each: technology name, version, 2-line justification grounded 
   in the extracted constraints.

3. Data Design Approach
   For each entity extracted from the FSD:
   SQL vs. NoSQL | Indexing needs | Audit/versioning required?

4. Security Architecture
   Map each FSD security requirement to a specific implementation:
   JWT structure and expiry | RBAC enforcement point | 
   Encryption approach (at rest + in transit) | 
   Rate limiting | Input validation layer

5. Integration Patterns
   For each API endpoint group:
   Synchronous REST vs. async event | Caching (yes/no, TTL, invalidation) | 
   Error handling (retry, circuit breaker, fallback)

Document all five decision areas as ADRs in TDD Section 2.1.

---

PHASE 3 — GENERATE THE TDD

Write the complete TDD using the sections below. 
Every section must draw directly from the extracted BRD/FSD content 
and the architectural decisions made in Phase 2.

═══════════════════════════════════════════════
SECTION 1 — DOCUMENT CONTROL
═══════════════════════════════════════════════

1.1 Document Header
    Title | Version (1.0) | Date | Author | Status (Draft) | Classification

1.2 Revision History
    | Version | Date | Author | Changes | Reviewed By |

1.3 Purpose and Scope
    What this TDD covers | What it does not cover | 
    Relationship to BRD, FSD, and API Spec

1.4 Definitions and Abbreviations
    Technical glossary for all acronyms and domain terms in this document

1.5 Reference Documents
    | Document | Version | Location |
    (BRD, FSD, OpenAPI Spec, Project Charter — from extraction)

═══════════════════════════════════════════════
SECTION 2 — SYSTEM ARCHITECTURE
═══════════════════════════════════════════════

2.1 Architecture Decision Records (ADRs)
    One ADR per major decision from Phase 2.
    Format per ADR:
    | Field          | Content                              |
    |----------------|--------------------------------------|
    | ADR ID         | ADR-001                              |
    | Decision       | [what was decided]                   |
    | Context        | [why a decision was needed]          |
    | Options        | [all options evaluated]              |
    | Chosen Option  | [selected choice]                    |
    | Rationale      | [why this option]                    |
    | Trade-offs     | [what this choice gives up]          |
    Minimum 6 ADRs: architecture style, frontend, backend, 
    database, auth, caching.

2.2 System Context
    Describe the system boundary in structured text:
    External Actors → Interface → System Components → Interface → External Systems
    For each connection: protocol | data format | direction | frequency

2.3 Architecture Layers
    Describe each layer and its components:
    
    Layer 1 — Client (Web / Mobile)
    Layer 2 — API Gateway / BFF
    Layer 3 — Application Services (one per functional domain from FSD)
    Layer 4 — Data (Database / Cache / Queue / Storage)
    Layer 5 — Infrastructure (Cloud / CDN / Load Balancer / Monitoring)
    
    For each component:
    Name | Responsibility (2 lines) | Technology | Connects to

2.4 Technology Stack Table
    | Layer | Component | Technology | Version | Justification |

2.5 Deployment Architecture
    | Environment | Purpose | Infrastructure | Access Control | Data Policy |
    Environments: Development | Staging | UAT | Production
    
    Production detail:
    Load balancing | Auto-scaling triggers | DB replication/failover | 
    CDN config | Backup strategy

═══════════════════════════════════════════════
SECTION 3 — COMPONENT DESIGN
═══════════════════════════════════════════════

For each application service identified from the FSD functional flows,
generate a Component Design Card:

    Component Name:
    Responsibility: (2–3 sentences)
    FSD Functions Covered: (FR ID reference)
    API Endpoints Owned: (from FSD extraction)
    
    Internal Modules:
    | Module | Responsibility | Pattern (Controller/Service/Repository/etc.) |
    
    Key Business Logic:
    Describe non-trivial processing in pseudocode or numbered steps.
    (Authentication flows, branching logic, state machines, 
     retry logic, notification routing — whatever applies per component)
    
    Inter-Service Communication:
    | Direction | Target/Source | Protocol | Trigger | Data |
    
    Error Handling:
    | Error Scenario | Detection Point | Response to Caller | Internal Action |
    
    Performance Notes:
    Caching, async offloading, or query optimisation decisions 
    specific to this component.

═══════════════════════════════════════════════
SECTION 4 — DATA DESIGN
═══════════════════════════════════════════════

4.1 Entity Relationship Overview
    For each entity extracted from the FSD:
    Entity | Key Attributes | Relationships (1:1 / 1:N / M:N) | Storage Type

4.2 Database Schema
    For each entity, produce a schema table:
    | Column | Data Type | Constraints | Default | Index? | Description |
    
    Mandatory conventions:
    - PKs: UUID (not auto-increment integer)
    - Every table: created_at, updated_at (TIMESTAMP), 
      is_deleted BOOLEAN DEFAULT false
    - Audit tables: created_by, updated_by (FK to Users)
    - String columns: explicit length (VARCHAR(255) not VARCHAR)
    - Enums: allowed values listed in Description column
    - FKs: named explicitly (fk_tablename_columnname)

4.3 Indexing Strategy
    | Table | Index Name | Columns | Type | Justification |
    Cover: all FKs, all filter/search columns, all status enum columns

4.4 Data Classification
    | Field | Entity | Classification | Encrypt at Rest? | Mask in Logs? | Retention |
    Levels: Public | Internal | Confidential | Restricted (PII/Sensitive)
    Flag all: email, phone, name, tokens, financial data, health data 
    — based on what the FSD reveals.

4.5 Migration Strategy
    Tool | Naming convention | Rollback approach | Seeding strategy per environment

4.6 Caching Design
    | Cache Key | Data Cached | TTL | Invalidation Trigger | Store |

═══════════════════════════════════════════════
SECTION 5 — API AND INTEGRATION DESIGN
═══════════════════════════════════════════════

5.1 API Design Principles
    Versioning | Pagination standard | Error response schema | 
    Idempotency policy | Content negotiation

5.2 API Security
    | Endpoint Group | Auth Required | Roles Permitted | Rate Limit | Controls |

5.3 End-to-End Request Flow (per functional requirement)
    For each FR, trace the full technical path:
    [Client] → [Gateway: action] → [Service: action] → 
    [Repository: query] → [Cache: hit/miss/write] → 
    [Response assembled] → [Client]
    Mark: auth validation point | RBAC check | cache check | DB operation type

5.4 Third-Party Integration Design
    | Integration | Provider Type | Protocol | Auth | 
      Timeout | Retry Policy | Fallback | Circuit Breaker? |

5.5 Async Processing Design
    Identify operations that must be async (not synchronous HTTP):
    | Operation | Trigger | Queue/Topic | Producer | Consumer | 
      Retry Policy | Dead Letter Queue? | Monitoring |

═══════════════════════════════════════════════
SECTION 6 — SECURITY DESIGN
═══════════════════════════════════════════════

6.1 Authentication Design
    JWT payload claims (list each: name | type | purpose) |
    Access token expiry | Signing algorithm (justify RS256 vs HS256) |
    Refresh token: expiry, rotation, storage, revocation |
    Logout: server-side invalidation mechanism |
    Multi-device session policy

6.2 Authorisation Design (RBAC)
    Role definitions:
    | Role | Description | Permitted Actions |
    
    Permission matrix (derive roles from FSD actors):
    | Resource | Role A | Role B | Role C | Admin |
    (✓ = permitted | ✗ = denied)
    
    RBAC enforcement: pseudocode for middleware role check

6.3 Data Security
    | Category | At-Rest Encryption | In-Transit | Log Masking | Access Control |
    
    Specify: column-level vs. disk-level encryption | TLS minimum version | 
    PII field list (exact column names from schema)

6.4 API Security Controls
    | Control | Implementation | Enforced At |
    Cover: rate limiting | input validation | SQL injection prevention | 
    XSS prevention | CORS policy | security headers | secrets management

6.5 Security Test Requirements
    | Test Type | Scope | Tool | Pass Criteria | Frequency |

═══════════════════════════════════════════════
SECTION 7 — NON-FUNCTIONAL DESIGN
═══════════════════════════════════════════════

Map each NFR extracted from the BRD to specific technical decisions:

7.1 Performance Design (for the response time NFR)
    Performance Budget:
    | Endpoint | Target p50 | Target p95 | Target p99 | Bottleneck Risk |
    
    Decisions: caching per endpoint | async offload candidates | 
    query optimisation rules | connection pool sizing | 
    compression (gzip/brotli — when applied)

7.2 Scalability Design (for the load NFR)
    Capacity Plan:
    | Component | Baseline | Target Load | Scaling Mechanism | Limit |
    
    Decisions: horizontal vs. vertical scaling per component | 
    auto-scaling trigger metric and thresholds | 
    DB read replicas | stateless confirmation (JWT = stateless — verify)

7.3 Availability Design (for the uptime NFR)
    Calculate allowable downtime per month from the uptime % in BRD.
    
    Decisions: health check endpoints (/health liveness, /ready readiness) |
    load balancer health check config | DB failover time |
    deployment strategy (rolling / blue-green / canary — justify) |
    graceful shutdown drain time

7.4 Observability Design
    Three pillars:
    
    Logging:
    | Field | Type | Example | PII? |
    (structured JSON log schema — list all fields)
    Log levels per environment | PII exclusion rules | Retention policy
    
    Metrics:
    | Metric Name | Type | Source | Alert Threshold |
    Application + infrastructure + business metrics
    
    Tracing:
    TraceId header name | Propagation across services | Sampling strategy

═══════════════════════════════════════════════
SECTION 8 — FRONTEND TECHNICAL DESIGN
═══════════════════════════════════════════════

8.1 Frontend Architecture
    Framework + version (justified) | State management | 
    Routing + route guards for auth | Code splitting strategy | 
    Build tooling

8.2 Component Tree (per screen from FSD UI behaviour notes)
    | Screen | Component Name | Type (Page/Container/UI) | Props | State | API Calls |

8.3 API Integration Layer
    HTTP client + config | JWT storage decision (HttpOnly cookie / 
    memory / localStorage — state security trade-off explicitly) |
    401 auto-refresh interceptor logic | 
    Global error handler | Request/response transformation

8.4 Mobile-Specific Design (if mobile is in FSD scope)
    Deep linking | Offline detection | Push notifications | 
    Biometric auth hooks

═══════════════════════════════════════════════
SECTION 9 — DEVOPS AND INFRASTRUCTURE
═══════════════════════════════════════════════

9.1 CI/CD Pipeline
    | Stage | Trigger | Actions | Pass Criteria | Fail Action |
    Stages: Commit → Lint/SAST → Unit Test → Build → Integration Test → 
    Security Scan → Deploy Staging → Smoke Test → Deploy UAT → 
    UAT Gate → Deploy Production → Production Smoke Test

9.2 Infrastructure as Code
    Tool choice (justified) | Repository structure | 
    State management | Environment promotion flow

9.3 Secrets Management
    Secrets store | Which secrets are managed | 
    Rotation policy per secret type | Runtime injection method

9.4 Monitoring and Alerting
    | Alert | Metric/Condition | Threshold | Severity | Channel | Runbook |
    Minimum alerts (derive thresholds from BRD NFRs):
    API error rate | Latency breach | Availability drop | 
    Security anomaly (failed login spike) | 
    DB connection saturation | Queue depth (if async)

═══════════════════════════════════════════════
SECTION 10 — TRACEABILITY AND SIGN-OFF
═══════════════════════════════════════════════

10.1 FSD-to-TDD Traceability Matrix
     | FSD Requirement ID | FSD Description | TDD Section | 
       Design Decision | Implementing Component |
     Every FSD functional flow and NFR must appear in at least one row.

10.2 Open Technical Decisions
     Items that cannot be resolved without stakeholder or product input.
     ALL unresolved items from the FSD open questions must appear here.
     | Decision ID | Question | Options | Recommended | Owner | Needed By |
     
     Rule: "TBD" is banned everywhere else in this document. 
     Every deferred item lives only in this table with an owner assigned.

10.3 TDD Approval
     | Role               | Name | Review Date | Status | Comments |
     |---------------------|------|-------------|--------|----------|
     | Solution Architect  |      |             |        |          |
     | Engineering Lead    |      |             |        |          |
     | Security Engineer   |      |             |        |          |
     | DevOps Lead         |      |             |        |          |
     | QA Architect        |      |             |        |          |
     | Product Manager     |      |             |        |          |

---

OUTPUT FORMAT RULES:
- Begin with the Pre-TDD Extraction Summary (Phase 1, Step 4) 
  BEFORE any TDD section — this confirms you have read the documents correctly
- Use ## for section headers: ## Section 1 — Document Control
- Use ### for subsections: ### 2.3 Architecture Layers
- All tables: proper markdown format
- Pseudocode: fenced code block tagged pseudocode
- SQL schemas: fenced code block tagged sql
- Architecture diagrams: structured indented text (no image generation)
- "TBD" is not permitted anywhere except Section 10.2
- After all sections: ## Technical Assumptions and Flags
  (numbered list of every assumption made and risk it introduces)

---

CONSTRAINTS:
- Every technology recommendation must reference a constraint from 
  the extracted BRD/FSD (team size, timeline, NFR, budget) — 
  no generic best-practice recommendations untethered to this project
- Every ADR must evaluate minimum 2 alternatives, not just the chosen option
- JWT storage recommendation must explicitly state the security trade-off 
  (there is no risk-free choice between HttpOnly cookie, localStorage, and memory)
- Schema must use UUID primary keys — auto-increment integers are not permitted
- RBAC permission matrix must derive roles from the FSD actors section — 
  do not invent roles not present in the FSD
- If the FSD has no mobile scope, Section 8.4 must be explicitly marked 
  "Not in scope per FSD Section [X]" rather than omitted silently
- Capacity planning numbers must be grounded in BRD NFRs — 
  do not invent baseline user volumes not stated in the source documents