# UAT Test Cases

## Project

AI-Powered Customer Support & Case Prioritization

## Purpose

The purpose of UAT is to validate that the proposed customer support case management solution meets the defined business requirements and supports expected business processes.

---

# UAT Test Cases

## UAT-01 – Create Customer Case

**Objective:**  
Verify that a customer can create a support case with the required information.

**Steps:**

1. Open the customer support portal.
2. Create a new support case.
3. Enter the required case information.
4. Submit the case.

**Expected Result:**

- A unique Case ID is generated.
- The case is successfully created.
- The submitted information is retained.

**Status:** Pass

---

## UAT-02 – Missing Mandatory Information

**Objective:**  
Verify that a case cannot be submitted when mandatory information is missing.

**Steps:**

1. Create a new support case.
2. Leave one or more mandatory fields empty.
3. Attempt to submit the case.

**Expected Result:**

The system identifies the missing information and prevents submission until the required information is provided.

**Status:** Pass

---

## UAT-03 – AI Case Classification

**Objective:**  
Verify that the system generates a recommended case category.

**Test Data:**

> "The customer is unable to access the application after the latest update."

**Expected Result:**

The system recommends an appropriate category such as:

**Product Issue / Technical Issue**

The recommendation should include a confidence indicator.

**Status:** Pass

---

## UAT-04 – Low AI Confidence

**Objective:**  
Verify that cases with low AI confidence are routed for manual review.

**Steps:**

1. Create a case with ambiguous or insufficient information.
2. Allow the AI classification process to run.

**Expected Result:**

- AI confidence is below the configured threshold.
- The case is flagged for manual review.
- The system does not automatically finalize the classification.

**Status:** Pass

---

## UAT-05 – P1 Priority Recommendation

**Objective:**  
Verify that a critical, high-impact case receives a P1 recommendation.

**Test Data:**

Customer Impact: High  
Issue Severity: Critical  
AI Confidence: High

**Expected Result:**

- Recommended Priority: P1 – Critical
- Case receives the appropriate SLA
- Appropriate support notification is triggered

**Status:** Pass

---

## UAT-06 – P4 Priority Recommendation

**Objective:**  
Verify that a low-impact general inquiry receives an appropriate lower priority.

**Test Data:**

Customer Impact: Low  
Issue Severity: Minor  
AI Confidence: High

**Expected Result:**

- Recommended Priority: P4 – Low
- Appropriate SLA is assigned
- Case is routed to the general support queue

**Status:** Pass

---

## UAT-07 – Human Override

**Objective:**  
Verify that an authorized support agent can override an AI recommendation.

**Steps:**

1. Open a case with an AI-generated priority.
2. Review the recommendation.
3. Change the priority.
4. Enter the reason for the override.
5. Save the case.

**Expected Result:**

- Final priority is updated.
- Override reason is recorded.
- User and timestamp are captured in the case history.

**Status:** Pass

---

## UAT-08 – Automatic Case Routing

**Objective:**  
Verify that a case is routed to the correct support team.

**Test Data:**

Category: Technical Issue

**Expected Result:**

The case is routed to the appropriate technical support team according to the approved routing rules.

**Status:** Pass

---

## UAT-09 – Routing Exception

**Objective:**  
Verify that cases without a matching routing rule are sent for manual review.

**Steps:**

1. Create a case that does not match an existing routing rule.
2. Complete case classification.

**Expected Result:**

The case is assigned to the designated manual review queue.

**Status:** Pass

---

## UAT-10 – SLA Assignment

**Objective:**  
Verify that the SLA is assigned according to final case priority.

**Test Data:**

Priority: P2 – High

**Expected Result:**

The system assigns the approved P2 response and resolution targets.

**Status:** Pass

---

## UAT-11 – SLA Risk Notification

**Objective:**  
Verify that a case approaching its SLA deadline is identified.

**Steps:**

1. Create an active case.
2. Allow the case to approach its configured SLA threshold.
3. Review the case status.

**Expected Result:**

The case is identified as SLA Risk and the appropriate support user or manager is notified.

**Status:** Pass

---

## UAT-12 – SLA Breach Escalation

**Objective:**  
Verify that a case exceeding its SLA is escalated.

**Steps:**

1. Create an active case with an assigned SLA.
2. Allow the SLA deadline to be exceeded.
3. Review the case.

**Expected Result:**

- Case is identified as SLA Breached.
- Appropriate escalation is triggered.
- Escalation event is recorded.

**Status:** Pass

---

## UAT-13 – AI Service Unavailable

**Objective:**  
Verify that support operations can continue when the AI service is unavailable.

**Steps:**

1. Create a new support case.
2. Simulate AI service unavailability.
3. Attempt to process the case.

**Expected Result:**

- Case remains available.
- Support agent can manually classify the case.
- Support agent can manually assign priority.
- Case processing can continue.

**Status:** Pass

---

## UAT-14 – Audit History

**Objective:**  
Verify that AI recommendations and human overrides are recorded.

**Steps:**

1. Create a case.
2. Allow an AI recommendation to be generated.
3. Override the recommendation.
4. Review case history.

**Expected Result:**

The history contains:

- AI recommendation
- Original value
- Updated value
- User
- Reason for change
- Date/time

**Status:** Pass

---

## UAT-15 – Priority Change and SLA Recalculation

**Objective:**  
Verify that the SLA is recalculated when case priority changes.

**Steps:**

1. Create a case with P3 priority.
2. Record the assigned SLA.
3. Change the priority to P1.
4. Save the case.

**Expected Result:**

- Priority changes from P3 to P1.
- Applicable P1 SLA is applied according to approved business rules.
- Appropriate notification is triggered.
- Priority change is recorded in case history.

**Status:** Pass

---

# UAT Summary

| Test Case | Scenario | Expected Outcome | Status |
|---|---|---|---|
| UAT-01 | Create Case | Case created successfully | Pass |
| UAT-02 | Missing Information | Submission prevented | Pass |
| UAT-03 | AI Classification | Category recommended | Pass |
| UAT-04 | Low AI Confidence | Manual review | Pass |
| UAT-05 | P1 Priority | P1 recommended | Pass |
| UAT-06 | P4 Priority | P4 recommended | Pass |
| UAT-07 | Human Override | Recommendation overridden | Pass |
| UAT-08 | Case Routing | Correct team assigned | Pass |
| UAT-09 | Routing Exception | Manual queue | Pass |
| UAT-10 | SLA Assignment | Correct SLA assigned | Pass |
| UAT-11 | SLA Risk | Alert triggered | Pass |
| UAT-12 | SLA Breach | Escalation triggered | Pass |
| UAT-13 | AI Unavailable | Manual processing available | Pass |
| UAT-14 | Audit History | Changes recorded | Pass |
| UAT-15 | Priority Change | SLA recalculated | Pass |

---

# UAT Outcome

The UAT scenarios cover the core business requirements, business rules, AI-related exception scenarios, SLA management, escalation, and audit requirements.

The solution should be approved for implementation only after all critical UAT scenarios have been successfully validated by the relevant business stakeholders.
