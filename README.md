# Billing Simulator v4 — Persistent Multi-Role Foundation

v4 adds:
- Student / Instructor / Admin role simulation
- Browser persistence using localStorage
- Organization user management
- Course and reusable patient records
- Activity and simulation authoring
- Seven-step simulation builder
- Basic, Inline, and Rubric grading views
- Grading report
- Rubric template editor
- Answer-key configuration
- Student simulation workspace
- Saved attempt records
- CBET competency/reporting foundation

This is a front-end prototype, not production authentication or a production database.
For production, move users, permissions, activities, patient data, attempts, scoring rules,
audit events, and uploaded documents to a secure server/database.

The architecture is informed by the public ChartFlow documentation: courses contain
activities; activities support simulation/template/new-patient experiences; grading can be
Basic, Inline, or Rubric; and answer keys and grading reports are supported. It is an
independent implementation for Billing Simulator, not copied source code or assets.


## v5 — Billing Chart Engine

The simulation workspace now has a billing-specific patient chart with linked sections:
- Visit Summary
- Patient Details
- Insurance
- Eligibility
- Encounters
- Diagnoses
- Procedures / Charges
- Claims
- EOB / Remittance
- Payments
- Denials
- A/R Follow-Up
- Follow-Up Notes
- Documents

It also adds simulated chart-entry creation and a persistent A/R queue. This is designed
for billing education rather than clinical care. The interface follows the conceptual
pattern documented by ChartFlow: a persistent patient chart, sidebar sections, visit
context, scenario clock, student/instructor shared chart experience, and grading/answer-key
workflow. It is independently implemented for Billing Simulator.


## FINAL — Simulation Control & Assessment Engine

The final build adds:
- Unfolding simulation events and scenario progress
- Event-triggered evidence progression
- Persistent learner action/audit logging
- Answer-key-based scoring
- Evidence-review and documentation scoring
- Instructor audit-log view
- Event-completion analytics
- Attempt history and average-score reporting
- JSON data export
- Persistent chart-entry events

Final architecture:
Organization → Roles → Courses → Activities → Patient Library → Billing Chart →
Claims/EOB/Denials/A/R → Simulation Engine → Answer Key → Grading → Reports → Audit.

This remains a browser prototype. Production deployment requires a secure backend,
server-side authentication/authorization, tenant isolation, encrypted storage,
privacy/security controls, backups, validation, and real database persistence.
Do not enter real PHI into this prototype.
