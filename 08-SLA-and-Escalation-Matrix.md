# SLA & Escalation Matrix

## Project

AI-Powered Customer Support & Case Prioritization

## 1. Purpose

This document defines the proposed Service Level Agreement (SLA) targets and escalation rules for customer support cases.

The purpose is to ensure that higher-impact customer issues receive faster attention and that cases at risk of SLA breach are identified and escalated appropriately.

---

# 2. SLA Definitions

### Response Time

The maximum time allowed for the support team to acknowledge or respond to a customer case.

### Resolution Time

The target time for resolving the customer issue.

### SLA Risk

A case is considered at risk when it approaches the defined SLA deadline without resolution.

### SLA Breach

A case is considered breached when the applicable SLA deadline has been exceeded.

---

# 3. Proposed SLA Matrix

| Priority | Description | Response Target | Resolution Target |
|---|---|---:|---:|
| P1 – Critical | Major customer/business impact | 30 minutes | 4 hours |
| P2 – High | Significant customer impact | 1 hour | 8 hours |
| P3 – Medium | Moderate impact | 4 hours | 2 business days |
| P4 – Low | Minor issue or general request | 1 business day | 5 business days |

> Note: SLA values are proposed portfolio assumptions and should be validated with business stakeholders before implementation.

---

# 4. Escalation Rules

| Event | Condition | Action | Escalated To |
|---|---|---|---|
| P1 Case Created | Critical priority | Immediate notification | Support Manager |
| P1 SLA Risk | 50% of resolution SLA elapsed | Priority alert | Support Manager |
| P1 SLA Breach | Resolution target exceeded | Immediate escalation | Support Manager + Escalation Team |
| P2 SLA Risk | 75% of resolution SLA elapsed | Alert | Support Manager |
| P2 SLA Breach | Resolution target exceeded | Escalation | Support Manager |
| P3 SLA Risk | 90% of resolution SLA elapsed | Alert | Assigned Team Lead |
| P3 SLA Breach | Resolution target exceeded | Escalation | Team Lead |
| P4 SLA Risk | 90% of resolution SLA elapsed | Reminder | Assigned Support Team |

---

# 5. Escalation Process

```text
Case Created
      ↓
Priority Confirmed
      ↓
SLA Assigned
      ↓
SLA Monitoring
      ↓
Is Case Approaching SLA?
      ↓
 ┌──────────────┐
 │              │
No             Yes
 │              │
 ↓              ↓
Continue       Alert
Processing      │
                ↓
         Is Case Resolved?
                ↓
        ┌───────────────┐
        │               │
       Yes              No
        │               │
        ↓               ↓
     Close         Escalate
                       │
                       ↓
               Manager / Team Lead
                       │
                       ↓
                  Continue
                  Resolution

6. SLA Business Rules
SLA-01

Every active customer case should have an applicable SLA based on its final priority.

SLA-02

P1 cases should receive the highest level of attention.

SLA-03

Cases approaching their SLA deadline should be identified before the deadline is exceeded.

SLA-04

SLA-breached cases should trigger the appropriate escalation.

SLA-05

Escalation notifications should be sent to the responsible support role.

SLA-06

SLA timers should be recalculated if the final priority changes.

SLA-07

Any manual change to priority should be recorded in the case history.

SLA-08

Cases should not be automatically closed solely because an SLA has been breached.

7. Priority Change Example

Consider a case initially classified as P3.

Initial State

Priority: P3
Resolution Target: 2 business days

The support agent identifies that the issue is affecting a major customer.

Priority Changed

P3 → P1

Expected System Behavior
Update the case priority
Apply the P1 SLA
Recalculate the SLA deadline according to approved rules
Trigger the appropriate P1 notification
Record the priority change and reason
Maintain an audit history
8. Exception Scenarios
Exception 01 – SLA Paused

If the business allows SLA pauses while waiting for customer information, the system should record:

Pause date/time
Reason
User
Resume date/time
Exception 02 – Business Hours

The business should define whether SLA calculations operate using:

24/7 calendar
Business hours
Regional support calendars
Exception 03 – Holidays

The business should define whether public holidays are excluded from SLA calculations.

Exception 04 – Reopened Cases

The business should define whether a reopened case receives:

A new SLA
The original SLA
A separate SLA based on the reopening event
9. Business Analyst Considerations

Before implementation, the following should be confirmed with stakeholders:

SLA targets
Business hours
Regional calendars
Holiday calendars
SLA pause conditions
Escalation thresholds
Escalation recipients
Priority change behavior
Reopened case behavior
Notification channels
10. Success Criteria

The SLA and escalation solution should provide:

Clear SLA targets for every priority
Visibility into SLA deadlines
Early identification of SLA risk
Timely escalation of breached cases
Accurate SLA recalculation when priority changes
Complete history of escalation events
