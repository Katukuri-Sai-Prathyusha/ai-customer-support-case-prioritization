# Requirement Gathering

## Project

AI-Powered Customer Support & Case Prioritization

## 1. Requirement Gathering Approach

Requirements were gathered by understanding the current customer support process, identifying pain points, and discussing business needs with customers, support agents, support managers, product stakeholders, and technical teams.

The focus was on understanding:

- How customer cases are currently created
- How cases are classified
- How priority is determined
- How cases are assigned to teams
- How SLA deadlines are managed
- How critical cases are escalated
- Where automation can reduce manual effort

---

## 2. Key Questions for Stakeholders

### Customer / End User

1. What type of issues do customers commonly report?
2. How do customers currently submit support requests?
3. What information is required when creating a support case?
4. How should urgent issues be identified?
5. What information should customers receive about their case?

### Support Agents

1. How do you currently classify incoming cases?
2. How do you determine whether a case is high or low priority?
3. What information helps you determine customer impact?
4. How are cases assigned to support teams?
5. What causes delays in case handling?
6. Which cases require immediate attention?
7. When should a case be escalated?
8. Should an AI-generated priority be automatically applied or reviewed by an agent?

### Support Managers

1. What SLA targets apply to different priorities?
2. Which cases should trigger escalation?
3. What information should appear on a support dashboard?
4. How should team workload be monitored?
5. Which KPIs should management track?

### Product Team

1. What case categories should be supported?
2. What business rules should determine priority?
3. Which fields should be mandatory?
4. What should happen when the AI cannot determine a category?
5. What should happen when the AI recommendation conflicts with the support agent's decision?

### Technical / AI Team

1. What data is required for case classification?
2. What historical case data is available?
3. What confidence level should be required for AI recommendations?
4. What should happen when AI confidence is low?
5. How should AI recommendations be recorded?
6. Should human approval be required before changing case priority?

---

## 3. Business Requirements

### BR-01 – Case Classification

The system should classify incoming customer cases into predefined categories.

Example categories:

- Technical Issue
- Product Issue
- Billing
- Account Request
- Service Disruption
- General Inquiry

### BR-02 – Priority Recommendation

The system should recommend a case priority based on defined business rules and relevant case information.

### BR-03 – Customer Impact

The system should consider customer impact when determining case priority.

### BR-04 – Case Routing

Cases should be routed to the appropriate support team based on case category and business rules.

### BR-05 – SLA Tracking

The system should calculate and track SLA deadlines based on case priority.

### BR-06 – Escalation

The system should identify cases approaching or exceeding their SLA and trigger the appropriate escalation.

### BR-07 – Human Review

Support agents should be able to review AI-generated classification and priority recommendations.

### BR-08 – Low Confidence Handling

Cases with low AI confidence should be flagged for manual review instead of being automatically prioritized.

### BR-09 – Auditability

The system should maintain a record of AI recommendations and subsequent human changes.

### BR-10 – Reporting

Management should have visibility into case volume, priority, SLA performance, escalations, and resolution trends.

---

## 4. Key Business Rules

| Rule ID | Business Rule |
|---|---|
| BRL-01 | Critical customer-impacting cases should receive the highest priority. |
| BRL-02 | Cases with low AI confidence should require human review. |
| BRL-03 | Priority should determine the applicable SLA. |
| BRL-04 | Cases should be routed based on case category and defined routing rules. |
| BRL-05 | Cases approaching their SLA deadline should be identified for escalation. |
| BRL-06 | Support agents should be able to override AI recommendations when required. |
| BRL-07 | AI recommendations and human overrides should be recorded for audit purposes. |

---

## 5. Example Requirement

### Business Need

Support managers need critical customer issues to receive immediate attention.

### Business Requirement

The system should identify cases with high customer impact and critical severity as high-priority cases.

### Expected Outcome

Critical cases should be prioritized and routed to the appropriate support team without unnecessary delay.

---

## 6. Requirement Clarifications

The following areas require further discussion before development:

- Definition of critical customer impact
- Priority levels and their criteria
- SLA targets for each priority
- AI confidence threshold
- Case categories
- Routing rules
- Escalation timing
- Human approval requirements
- Data retention requirements
- Reporting requirements
- Exception handling

---

## 7. Requirement Validation

Before finalizing requirements, the Business Analyst should review them with relevant stakeholders to confirm:

- Requirements are clear
- Requirements are complete
- Requirements are feasible
- Requirements are testable
- Business rules are agreed upon
- Exceptions are identified
- Stakeholder expectations are aligned
