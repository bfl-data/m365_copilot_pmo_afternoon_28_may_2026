# Business Requirements Document – App Adoption (DIY Servicing Feature)

## 1. Document Header
- Document Title: Business Requirements Document – App Adoption (DIY Servicing Feature)
- Version: 1.0
- Date: 27 May 2026
- Author: Business Analyst
- Status: Draft

## 2. Executive Summary
The App Adoption feature enables end users to perform DIY servicing activities through the mobile and web application, reducing dependency on manual or assisted service channels. This initiative aims to drive digital adoption, lower operational costs, and improve user experience through self-service capabilities. The expected outcome is increased digital engagement and a measurable reduction in service-related costs.

## 3. Business Objectives
- Increase app adoption rate among end users by 30% within 6 months of launch
- Reduce assisted customer service requests by 25% within 6 months
- Achieve at least 60% of service requests via self-service channels
- Decrease average service handling cost by 20%
- Improve customer satisfaction (CSAT) for servicing journeys to >85%

## 4. Scope
### In Scope:
- DIY servicing across platforms
- Service request workflows
- Notifications and tracking
- Knowledge base and FAQs

### Out of Scope:
- Backend overhaul
- Offline servicing

## 5. Stakeholders
| Stakeholder | Role | Responsibility |
|-------------|------|----------------|
| Product Manager | Owner | Define roadmap |
| Engineering | Dev | Build solution |
| QA | Testing | Quality checks |

## 6. Functional Requirements
1. FR-01 | Login and access | High
2. FR-02 | Service catalogue | High
3. FR-03 | Submit requests | High
4. FR-04 | Guided troubleshooting | High
5. FR-05 | Track requests | High

## 7. Non-Functional Requirements
- Performance: <3 sec response
- Security: Encryption + RBAC
- Scalability: 2x user load support
- Availability: 99.5% uptime

## 8. User Stories
- As a user, I want to view services so that I can resolve issues
- As a user, I want to raise requests digitally
- As a user, I want tracking updates

## 9. Assumptions & Dependencies
### Assumptions:
- Users have access to app
- Backend supports integration

### Dependencies:
- API readiness
- UX delivery timeline

## 10. Risks & Mitigations
| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| Low adoption | Medium | High | Awareness campaigns |
| Tech delays | High | High | Agile rollout |

## 11. Success Metrics
- Adoption rate
- Ticket reduction
- Cost savings
- CSAT score

## 12. Open Questions
- Priority services?
- Communication channels?
- Compliance constraints?

## 13. ROI Analysis & Business Justification

### 13.1 Cost Estimate (One-Time)
| Cost Item              | Estimated Cost | Notes                  |
|------------------------|----------------|------------------------|
| Development effort     | ₹80,00,000     | 8–10 member team / 4–5 sprints |
| Infrastructure/tooling | ₹15,00,000     | Cloud hosting, APIs, licenses |
| QA & Testing           | ₹12,00,000     | Functional and performance testing |
| Training & Rollout     | ₹8,00,000      | Internal training, onboarding |
| **Total One-Time Cost**| ₹1,15,00,000   |                        |

### 13.2 Ongoing Cost (Annual)
| Cost Item              | Estimated Cost | Notes       |
|------------------------|----------------|-------------|
| Maintenance & Support  | ₹20,00,000     | Bug fixes, enhancements |
| Infrastructure (run)   | ₹12,00,000     | Hosting and scaling |
| **Total Annual Cost**  | ₹32,00,000     |             |

### 13.3 Quantifiable Benefits (Annual)
| Benefit                        | Basis of Estimate       | Value/Year  |
|--------------------------------|-------------------------|-------------|
| Support ticket reduction       | 25% reduction × volume  | ₹37,50,000 |
| Operational cost savings       | Reduced manual effort   | ₹30,00,000 |
| Increased digital adoption     | Lower servicing cost    | ₹25,00,000 |
| Faster turnaround              | Productivity gains      | ₹10,00,000 |
| **Total Annual Benefit**       |                         | ₹1,02,50,000 |

### 13.4 ROI Summary
| Metric                  | Value              |
|-------------------------|--------------------|
| Total Investment (Yr 1) | ₹1,47,00,000       |
| Total Annual Benefit    | ₹1,02,50,000       |
| Net ROI (Year 1)        | ₹-44,50,000        |
| ROI %                   | -30.27%            |
| Payback Period          | ~18–20 months      |

### 13.5 Qualitative & Strategic Value
- Accelerates digital transformation
- Reduces dependency on manual processes
- Enhances customer experience
- Strengthens competitive positioning
- Enables future automation capabilities

### 13.6 Assumptions & Caveats
- Costs are indicative and subject to change
- Benefits based on historical servicing data
- ROI excludes indirect benefits like brand value