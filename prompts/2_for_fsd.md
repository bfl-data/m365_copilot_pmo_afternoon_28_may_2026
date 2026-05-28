You are a senior Business Analyst and Functional Architect with 10+ years of experience 
translating BRDs into detailed Functional Specification Documents (FSDs) for enterprise 
digital products.

I am providing you with a Business Requirements Document (BRD) for an App Adoption / 
DIY Servicing feature. Your task is to generate a comprehensive, professional-grade FSD 
based on the BRD content.

---

**CONTEXT:**
- Product: Mobile and web application with DIY self-servicing capabilities
- Audience for FSD: Development engineers, solution architects, QA engineers, and UX designers
- Purpose: The FSD must be detailed enough for the engineering team to begin design and 
  development without further clarification from business stakeholders.

---

**YOUR TASK — Think through each section in order before writing:**

Step 1: Review each functional requirement (FR-01 to FR-05) in the BRD and expand it 
into a full functional specification — including feature description, actors/roles involved, 
preconditions, main flow, alternate flows, and exception/error flows.

Step 2: For each functional requirement, define acceptance criteria in Gherkin format 
(Given / When / Then).

Step 3: Specify UI/UX behaviour for each feature — screen name, key UI elements, 
validation rules, and user guidance messages (do not design actual wireframes, but 
describe the expected screen layout and interactions in structured text).

Step 4: Define the API/integration touchpoints implied by each functional requirement — 
endpoint purpose, input parameters, expected response, and error codes.

Step 5: Map all non-functional requirements (performance, security, scalability, 
availability) to specific system behaviour and testable benchmarks.

Step 6: Generate a Traceability Matrix mapping each FSD section back to the originating 
BRD section and functional requirement ID.

---

**OUTPUT FORMAT — Produce the FSD as a structured markdown document with these sections:**

1. Document Header (Title, Version, Date, Author, Status, Revision History)
2. Purpose and Scope (reference the BRD scope, clarify what FSD adds)
3. System Overview (brief architecture context — mobile + web + backend APIs)
4. Actors and Roles (end user, admin, support agent — define each)
5. Functional Specifications (one subsection per FR-01 to FR-05, each containing):
   - Feature Description
   - Actors Involved
   - Preconditions
   - Main Flow (numbered steps)
   - Alternate Flows
   - Exception / Error Flows
   - Acceptance Criteria (Gherkin)
   - UI Behaviour Notes
   - API / Integration Notes
6. Non-Functional Specifications (expand each NFR to measurable system behaviour)
7. Data Requirements (data entities, key fields, validation rules)
8. Security and Compliance Specifications
9. Notification and Communication Specifications (aligned to BRD scope)
10. Traceability Matrix (FSD Section → BRD Section → FR ID)
11. Open Issues and Assumptions (incorporate BRD open questions + new ones identified)
12. Glossary

---

**CONSTRAINTS:**
- Do not invent business rules not implied by the BRD — flag gaps as open questions instead
- Use formal, precise language suitable for a technical specification document
- Every functional flow must have at least one alternate flow and one error/exception flow
- Acceptance criteria must be testable — avoid vague language like "system should work correctly"
- Label every section with a section number for easy cross-referencing

---

**INPUT — BRD content is attached**
