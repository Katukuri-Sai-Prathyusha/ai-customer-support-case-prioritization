# As-Is and To-Be Process Analysis

## Project

AI-Powered Customer Support & Case Prioritization

---

# 1. As-Is Process

Currently, customer support cases are manually reviewed and classified by support agents.

## Current Process Flow

```text
Customer Submits Case
        ↓
Case Created
        ↓
Support Agent Reviews Case
        ↓
Agent Identifies Category
        ↓
Agent Determines Priority
        ↓
Agent Assigns Support Team
        ↓
Agent Starts Investigation
        ↓
SLA Manually Monitored
        ↓
Issue Resolved
        ↓
Case Closed
Current Process Challenges
Manual case classification
Inconsistent priority assignment
Time spent reviewing repetitive cases
Incorrect team assignment
Limited visibility into SLA risk
Critical cases may not be identified quickly
Manual escalation activities
2. To-Be Process

The proposed process introduces AI-assisted classification and prioritization while keeping human review and decision-making in the workflow.

Proposed Process Flow
Customer Submits Case
        ↓
Case Created
        ↓
AI Analyzes Case
        ↓
Category Recommendation
        ↓
Priority Recommendation
        ↓
Confidence Check
        ↓
   ┌───────────────┐
   │               │
High Confidence   Low Confidence
   │               │
   ↓               ↓
Agent Review      Manual Review
   │               │
   └───────┬───────┘
           ↓
   Final Priority Confirmed
           ↓
    Automatic Routing
           ↓
      SLA Assigned
           ↓
      SLA Monitoring
           ↓
   ┌───────────────┐
   │               │
Within SLA     SLA at Risk
   │               │
   ↓               ↓
Continue         Escalation
   │               │
   └───────┬───────┘
           ↓
      Issue Resolved
           ↓
       Case Closed
3. Process Comparison
Process Area	As-Is	To-Be
Case Classification	Manual	AI-assisted
Priority Assignment	Manual	AI recommendation + human review
Confidence Handling	Not applicable	Low-confidence cases flagged
Team Routing	Manual	Rule-based / automated
SLA Assignment	Manual / existing process	Automatically assigned based on priority
SLA Monitoring	Manual	Automated monitoring
Escalation	Manual	Automated alerts/escalation
Auditability	Limited	AI recommendation and overrides recorded
Management Visibility	Limited	KPI and reporting visibility
4. Process Gaps Identified

The following gaps were identified between the current and proposed process:

Gap 01 – Manual Classification

Support agents spend time manually categorizing incoming cases.

Gap 02 – Inconsistent Prioritization

Different agents may interpret severity and customer impact differently.

Gap 03 – SLA Risk

Cases approaching SLA deadlines may not be identified early enough.

Gap 04 – Manual Routing

Cases may require manual assignment to the correct support team.

Gap 05 – Limited AI Governance

There is currently no defined process for handling AI recommendations, low-confidence results, or human overrides.

5. Proposed Process Improvements

The proposed process aims to:

Reduce manual classification effort
Improve consistency of case prioritization
Identify critical cases earlier
Improve support team routing
Improve SLA visibility
Automate escalation activities
Maintain human oversight of AI recommendations
Capture AI decisions and human overrides for audit purposes
6. Business Analyst Analysis

The To-Be process introduces automation while maintaining human oversight for business-critical decisions.

AI recommendations should support support agents rather than completely replace human decision-making.

The final solution should be validated against business requirements, operational policies, SLA commitments, and stakeholder expectations before implementation.
