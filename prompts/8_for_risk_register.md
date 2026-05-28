You are a Senior Risk Manager and PMO Lead with expertise in managing 
risks across digital product delivery programmes.

Using the attached BRD, FSD, TDD, Project Plan / WBS, and Resource 
Plan as your source of truth, generate a comprehensive Risk Register 
for the App Adoption (DIY Servicing Feature).

The document must include:

1. **Risk Register Overview**
   - Purpose and scope of the risk register
   - Risk management approach (Identify → Assess → Respond → Monitor)
   - Risk appetite statement derived from BRD business objectives
   - Review cadence and ownership model

2. **Risk Identification**
   Identify risks across these categories:

   * **Business & Strategic Risks**
     - Low app adoption despite feature launch
     - Misalignment between business objectives and delivery
     - Stakeholder change or priority shifts

   * **Technical Risks**
     - API readiness and integration failures
     - Performance under 2x load (NFR from FSD)
     - Security vulnerabilities (HTTPS, RBAC gaps)
     - Technical debt from accelerated delivery

   * **Resource & People Risks**
     - Key person dependency / attrition
     - Skill gaps identified in Resource Plan
     - Vendor or contractor delivery risk

   * **Schedule & Delivery Risks**
     - Sprint overruns impacting Go-Live
     - UAT feedback causing scope creep
     - Dependency delays (API, UX, infrastructure)

   * **Financial Risks**
     - Cost overrun beyond ₹1,15,00,000 one-time budget
     - ROI not achieved within 18–20 month payback period
     - Benefit realisation shortfall

   * **Compliance & Security Risks**
     - Data privacy and encryption gaps
     - Role-based access control failures
     - Regulatory or audit findings

   * **Change Management & Adoption Risks**
     - User resistance to self-service model
     - Inadequate training and onboarding
     - Communication gaps during rollout

3. **Risk Assessment**
   For each identified risk provide:
   - Risk ID (RISK-001, RISK-002...)
   - Risk Category
   - Risk Description
   - Root Cause
   - Likelihood: 🔴 High | 🟡 Medium | 🟢 Low
   - Impact: 🔴 High | 🟡 Medium | 🟢 Low
   - Risk Score (Likelihood × Impact: 1–9 matrix)
   - Risk Owner (role, not person)

4. **Risk Response Plan**
   For each risk, define:
   - Response Strategy: Avoid | Mitigate | Transfer | Accept
   - Specific mitigation actions
   - Contingency plan if risk materialises
   - Trigger point / Early warning indicator
   - Target residual risk level after mitigation

5. **Risk Heat Map**
   - 3×3 matrix (Likelihood vs Impact)
   - Place each Risk ID in the appropriate cell
   - Highlight top 5 critical risks

6. **Risk Prioritisation Table**
   - Sort all risks by Risk Score (High to Low)
   - Flag top 3 as [CRITICAL - IMMEDIATE ACTION]
   - Flag risks linked to BRD open questions as [OPEN QUESTION RISK]

7. **Risk Monitoring & Escalation**
   - Review frequency per risk tier
   - Escalation path: Team Lead → PM → Steering Committee
   - Risk closure criteria
   - How risks will be tracked (JIRA / Risk log tool)

8. **Assumptions Log**
   - List all assumptions made during risk identification
   - Flag assumptions that if proven wrong become risks
   - Format: Assumption | If Wrong → Risk | Likelihood

9. **Dependency Risk Map**
   - Map inter-phase and cross-team dependencies
   - Identify which dependencies are on the critical path
   - Flag unresolved dependencies as [DEPENDENCY UNRESOLVED]

10. **Risk Register Summary Dashboard**
    - Total risks identified by category
    - Risk distribution by severity
    - Top 5 risks with owners and next review date
    - Overall project risk rating: 🔴 High | 🟡 Medium | 🟢 Low

Output Format:
- Structured document with clear section headers
- Master risk table with all risks in one consolidated view
- Separate heat map table (3×3 grid using text/ASCII)
- All financial figures in INR (₹)
- Flag risks derived from BRD open questions as [FROM OPEN QUESTIONS]
- Flag newly identified risks not in BRD as [NEW RISK IDENTIFIED]
- Flag items needing stakeholder validation as [VALIDATE WITH STAKEHOLDER]