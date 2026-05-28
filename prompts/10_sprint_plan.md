You are a Senior Scrum Master and Agile Delivery Lead with expertise 
in sprint planning for digital product programmes.

Using the attached BRD, FSD, TDD, Project Plan / WBS, Resource Plan,
Risk Register, and RACI Matrix as your source of truth, generate a 
comprehensive Sprint Plan for the App Adoption (DIY Servicing Feature).

The document must include:

1. **Sprint Planning Overview**
   - Agile delivery approach and methodology
   - Sprint duration: 2 weeks per sprint
   - Total number of sprints (derive from WBS estimates)
   - Sprint calendar: Start date, end date, key ceremonies
   - Definition of Ready (DoR) for user stories
   - Definition of Done (DoD) for sprint completion
   - Velocity assumption (story points per sprint per team)

2. **Team Capacity Plan**
   - Team composition per sprint (derive from Resource Plan)
   - Available person-days per sprint after accounting for:
     * Public holidays
     * Ceremony overhead (standup, planning, retro, review)
     * Leave buffer (10-15%)
   - Capacity table: Role | Total Days | Available Days | 
     Ceremony Days | Net Capacity

3. **Product Backlog (Master)**
   - Full list of user stories derived from BRD and FSD
   - Format for each story:
     * Story ID (US-001, US-002...)
     * User Story statement (As a... I want... So that...)
     * Acceptance Criteria (Given / When / Then)
     * Story Points estimate
     * Priority: 🔴 Must Have | 🟡 Should Have | 🟢 Nice to Have
     * Linked FR (FR-01 to FR-05)
     * Dependencies

   Cover stories across:
   * Authentication and Login (FR-01)
     - OTP login flow
     - Credential login flow
     - Session management
     - Error and lockout handling

   * Service Catalogue (FR-02)
     - Service listing and display
     - Search functionality
     - Filter functionality
     - Empty and error states

   * Submit Requests (FR-03)
     - Request form with validation
     - Request ID generation
     - Confirmation screen
     - Draft save functionality

   * Guided Troubleshooting (FR-04)
     - Step-by-step flow rendering
     - Decision tree navigation
     - Escalate to request option
     - Progress save and resume

   * Track Requests (FR-05)
     - Request status view
     - Timeline and history
     - Notification on status change
     - Filter by status

   * Non-Functional & Infrastructure Stories
     - Performance optimisation (<3 sec response)
     - Security implementation (HTTPS, RBAC)
     - Scalability setup (2x load)
     - Availability configuration (99.5% uptime)

   * DevOps and CI/CD Stories
     - Pipeline setup
     - Environment configuration (Dev/QA/UAT/Prod)
     - Monitoring and alerting setup

4. **Sprint-wise Breakdown**
   For each sprint provide:

   * Sprint Header:
     - Sprint number and name
     - Sprint goal (one clear statement)
     - Start and end dates
     - Team capacity (person-days)

   * Sprint Backlog:
     - Story ID | Story Summary | Story Points | 
       Assignee Role | Status
     - Total story points committed vs capacity

   * Sprint Milestones:
     - Key deliverables due within this sprint
     - Dependencies that must be resolved before sprint start

   * Sprint Risks:
     - Risks specific to this sprint (link to Risk Register)
     - Mitigation action for each

   * Sprint Ceremonies Schedule:
     - Sprint Planning | Daily Standup | Mid-Sprint Check |
       Sprint Review | Sprint Retrospective

   Suggested Sprint Structure:
   - Sprint 0: Environment setup, tooling, team onboarding
   - Sprint 1–2: FR-01 (Login) + FR-02 (Service Catalogue) - Core
   - Sprint 3–4: FR-03 (Submit Requests) + FR-04 (Troubleshooting)
   - Sprint 5: FR-05 (Track Requests) + Notifications
   - Sprint 6: Integration, NFR implementation, performance tuning
   - Sprint 7: Bug fixing, regression, UAT preparation
   - Sprint 8: UAT support, defect fixes, Go-Live prep
   - Buffer Sprint: Contingency for overflows and UAT feedback

5. **Dependency Map Across Sprints**
   - Visual (text/ASCII) showing inter-sprint dependencies
   - Highlight stories that block subsequent sprint starts
   - Flag unresolved cross-team dependencies as 
     [DEPENDENCY UNRESOLVED]

6. **Release Plan**
   - Map sprints to releases:
     * Alpha Release (internal): After Sprint 4
     * Beta Release (limited users): After Sprint 6
     * Production Release (Go-Live): After Sprint 8
   - Release criteria for each milestone
   - Rollback plan per release

7. **Velocity Tracking Plan**
   - How velocity will be tracked sprint over sprint
   - Burn-down and burn-up chart guidance
   - Threshold for raising a delivery risk flag:
     * <70% velocity → [VELOCITY RISK - ESCALATE]
     * >90% velocity for 2 sprints → consider scope addition

8. **Backlog Refinement Plan**
   - Refinement cadence: Mid-sprint, weekly
   - Who attends: PO, BA, Tech Lead, Scrum Master
   - Entry and exit criteria for stories entering refinement
   - Story splitting guidelines for oversized stories (>8 pts)

9. **UAT Sprint Plan**
   - Dedicated UAT sprint activities:
     * Test scenario preparation
     * Business user onboarding
     * Defect logging and triage
     * Sign-off checklist
   - UAT entry criteria (what must be true before UAT starts)
   - UAT exit criteria (what must be true before Go-Live)

10. **Sprint Metrics & Reporting**
    - Metrics tracked per sprint:
      * Planned vs completed story points
      * Defect injection rate
      * Defect resolution rate
      * Sprint goal achieved: Yes / Partial / No
    - Reporting format for Steering Committee
    - Escalation trigger: 2 consecutive sprints below 70% velocity

Output Format:
- Structured document with clear section headers
- Master backlog as a consolidated table
- Individual sprint cards with backlog, capacity, goal, 
  risks, and ceremonies
- Dependency map in ASCII/text grid format
- Release plan as a timeline table
- All story points and capacity figures clearly stated
- Flag stories with unclear acceptance criteria as 
  [STORY NEEDS REFINEMENT]
- Flag dependencies on external teams as [EXTERNAL DEPENDENCY]
- Flag assumptions as [ASSUMED]
- Flag items needing PO confirmation as [PO SIGN-OFF NEEDED]