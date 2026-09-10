# Business Rules & Decision Table

## Project

AI-Powered Customer Support & Case Prioritization

## 1. Purpose

This document defines the business rules used to classify and prioritize customer support cases.

The rules provide a consistent approach for determining case priority based on customer impact, issue severity, and business urgency.

---

# 2. Priority Levels

The solution will use four priority levels:

| Priority | Description | Example |
|---|---|---|
| P1 – Critical | Immediate business/customer impact | Major service outage affecting multiple customers |
| P2 – High | Significant impact requiring urgent attention | Important functionality unavailable |
| P3 – Medium | Normal business impact | Product issue affecting limited functionality |
| P4 – Low | Minimal impact | General question or minor request |

---

# 3. Business Rules

### BR-01 – Critical Impact

If a customer reports a critical issue affecting a major business function or service, the case should be considered for P1 priority.

### BR-02 – High Impact

If an issue significantly affects the customer's business but does not meet P1 criteria, the case should be considered for P2 priority.

### BR-03 – Medium Impact

If an issue has limited business impact and does not require immediate attention, the case should be considered for P3 priority.

### BR-04 – Low Impact

General questions, informational requests, and minor issues should normally be considered P4 priority.

### BR-05 – Customer Impact Override

If customer impact is significantly higher than the initial AI recommendation, the support agent should be able to increase the priority.

### BR-06 – Human Review

Cases where AI confidence is below the defined threshold should be sent for manual review.

### BR-07 – Critical Case Review

Cases classified as P1 should require confirmation by an authorized support user before final priority is applied, unless an approved business rule allows automatic prioritization.

### BR-08 – SLA Assignment

The final priority should determine the applicable SLA.

### BR-09 – Escalation

Cases approaching their SLA deadline should be identified for escalation.

### BR-10 – Audit Trail

AI recommendations and human changes to priority should be recorded.

---

# 4. Decision Table

The following decision table illustrates how case priority can be determined.

| Condition | Scenario 1 | Scenario 2 | Scenario 3 | Scenario 4 | Scenario 5 |
|---|---|---|---|---|---|
| Customer Impact | High | High | Medium | Low | Low |
| Issue Severity | Critical | Major | Major | Minor | Minor |
| AI Confidence | High | High | High | High | Low |
| Recommended Priority | P1 | P2 | P2 | P4 | Manual Review |
| Human Review Required | Yes | No | No | No | Yes |

---

# 5. Example Decision Scenarios

## Scenario 1 – Major Service Outage

**Customer Impact:** High  
**Issue Severity:** Critical  
**AI Confidence:** High

### Expected Outcome

- Recommended Priority: P1
- Human Review: Required
- SLA: Critical SLA
- Escalation: Immediate notification to the appropriate support team

---

## Scenario 2 – Important Feature Not Working

**Customer Impact:** High  
**Issue Severity:** Major  
**AI Confidence:** High

### Expected Outcome

- Recommended Priority: P2
- Human Review: Not required unless business rules specify otherwise
- SLA: High-priority SLA
- Routing: Appropriate technical support team

---

## Scenario 3 – Limited Product Issue

**Customer Impact:** Medium  
**Issue Severity:** Major  
**AI Confidence:** High

### Expected Outcome

- Recommended Priority: P2
- SLA: High-priority SLA
- Routing: Appropriate product/support team

---

## Scenario 4 – General Question

**Customer Impact:** Low  
**Issue Severity:** Minor  
**AI Confidence:** High

### Expected Outcome

- Recommended Priority: P4
- SLA: Low-priority SLA
- Routing: General support team

---

## Scenario 5 – Low AI Confidence

**Customer Impact:** Low  
**Issue Severity:** Minor  
**AI Confidence:** Low

### Expected Outcome

- AI should not automatically finalize the priority
- Case should be flagged for manual review
- Support agent determines the final priority

---

# 6. Priority Decision Flow

```text
Case Created
     ↓
AI Analyzes Case
     ↓
Evaluate Customer Impact
     ↓
Evaluate Issue Severity
     ↓
Check AI Confidence
     ↓
   ┌───────────────────┐
   │                   │
High Confidence    Low Confidence
   │                   │
   ↓                   ↓
Recommend Priority   Manual Review
   │                   │
   └─────────┬─────────┘
             ↓
       Human Validation
             ↓
       Final Priority
             ↓
        SLA Assigned
             ↓
     Case Routed / Managed
7. Business Analyst Considerations

Before implementation, the following should be confirmed with stakeholders:

Exact definition of customer impact
Exact definition of severity
AI confidence threshold
P1 approval requirements
Priority override permissions
SLA targets
Escalation timing
Support team routing rules
Audit requirements
Exception handling

The decision table should be reviewed with business and technical stakeholders before being finalized.
