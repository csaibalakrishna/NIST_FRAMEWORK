# Day 5 — NIST Cybersecurity Framework (CSF) 2.0: RESPOND

## Objective

Understand the RESPOND Function from a SOC / Blue Team perspective and learn how an organization manages, analyzes, communicates about, and mitigates a cybersecurity incident.

**Primary reference:** NIST Cybersecurity Framework (CSF) 2.0, CSWP 29  
https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.29.pdf

Official CSF website: https://www.nist.gov/cyberframework

---

## 1. What is the RESPOND Function?

The RESPOND Function focuses on taking action regarding a detected cybersecurity incident. It includes incident management, incident analysis, response reporting and communication, and incident mitigation.

The four RESPOND categories are:

- **RS.MA — Incident Management**
- **RS.AN — Incident Analysis**
- **RS.CO — Incident Response Reporting and Communication**
- **RS.MI — Incident Mitigation**

## 2. RESPOND Categories from a SOC Perspective

### RS.MA — Incident Management

**Purpose:** Manage and coordinate the incident response process.

SOC-related activities include:

- Validate and triage the incident report.
- Categorize and prioritize the incident using organizational criteria.
- Follow the organization's incident response plan and playbooks.
- Document the incident and actions taken.
- Escalate to the appropriate team or authority according to procedure.
- Coordinate response activities.

**Example:** A SIEM alert indicates possible account compromise. The analyst validates the alert, assigns an appropriate priority based on the available evidence and severity criteria, documents the findings, and escalates it to the incident response team.

**Interview-ready answer:**

> I would validate the incident, categorize and prioritize it according to the organization's severity criteria, document the findings, and escalate it to the appropriate incident response team according to the playbook.

### RS.AN — Incident Analysis

**Purpose:** Analyze the incident to understand what happened, how it happened, and what may have been affected.

SOC-related activities include:

- Correlate authentication, endpoint, and network logs.
- Reconstruct the incident timeline.
- Identify affected accounts, devices, and other assets.
- Investigate the activities performed during the incident.
- Investigate the likely root cause where possible.
- Estimate the scope and impact.
- Preserve evidence and document investigative actions.

**Example:** Correlate failed logins, a successful login from an unusual IP, PowerShell execution, and a large outbound connection to establish a timeline and investigate the possible account compromise.

**Interview-ready answer:**

> I would correlate authentication, endpoint, and network logs to reconstruct the incident timeline, identify affected assets and activities, investigate the likely root cause, and estimate the scope and impact while preserving evidence.

### RS.CO — Incident Response Reporting and Communication

**Purpose:** Communicate relevant incident information to the appropriate stakeholders according to organizational policies and applicable requirements.

SOC-related activities include:

- Notify the SOC lead or incident response team through the defined escalation process.
- Communicate verified findings and clearly label unconfirmed hypotheses.
- Share the incident timeline, affected assets, current impact, and actions taken.
- Record outstanding questions, risks, and follow-up actions.
- Follow the organization's internal and external communication procedures.
- Support any required external notifications through the appropriate authorized personnel.

**Example:** Inform the designated incident response stakeholders about the suspected account compromise, affected workstation, evidence collected, containment actions, and current understanding of the impact.

**Interview-ready answer:**

> I would notify the relevant SOC lead and incident response stakeholders, providing the incident timeline, affected assets, verified findings, actions taken, and current impact. I would follow the organization's communication and escalation procedures.

### RS.MI — Incident Mitigation

**Purpose:** Contain the incident and eradicate the threat.

- **Containment** limits the incident's spread or ongoing effects.
- **Eradication** removes malicious artifacts, persistence mechanisms, or the identified cause, as appropriate to the incident.

SOC-related activities may include:

- Recommend or perform approved isolation of an affected endpoint.
- Disable or restrict a compromised account when authorized.
- Block malicious indicators where appropriate and authorized.
- Remove malicious artifacts or persistence mechanisms with the response team.
- Address the identified cause so the same threat is less likely to continue.
- Verify that mitigation actions are effective.

**Example:** If unauthorized access is confirmed, the response team may disable the compromised account, isolate the affected workstation, and investigate and remove malicious artifacts according to the response plan.

**Interview-ready answer:**

> I would follow the incident response plan to contain the threat, for example by isolating an affected endpoint or disabling a compromised account when authorized. Then I would support eradication by removing malicious artifacts, persistence mechanisms, or the identified cause.

**Important:** A Tier 1 SOC analyst should follow organizational authorization and escalation procedures. Do not assume you can independently isolate any system or disable any account.

---

## 3. Practical SOC Scenario

### Scenario

A SIEM alert shows:

- Multiple failed logins for an employee account.
- A successful login from an unusual IP address.
- Suspicious PowerShell execution on the employee's workstation.
- A large outbound network connection to an external IP.

The investigation confirms unauthorized access to the account, but the full impact is not yet known.

### How RESPOND applies

| Category | Practical response |
|---|---|
| **RS.MA — Incident Management** | Validate and prioritize the incident, document findings, follow the playbook, and escalate to the incident response team. |
| **RS.AN — Incident Analysis** | Correlate authentication, endpoint, and network evidence; build a timeline; identify affected assets; and estimate scope and impact. |
| **RS.CO — Reporting and Communication** | Notify designated stakeholders and communicate verified findings, actions taken, current impact, and outstanding risks. |
| **RS.MI — Incident Mitigation** | Contain the threat and support eradication using authorized, incident-appropriate actions. |

Do not assume that the large outbound connection proves data exfiltration. Investigate the destination, traffic details, endpoint activity, and other evidence before making that conclusion.

---

## 4. RESPOND vs. RECOVER

RESPOND and RECOVER are related but have different purposes.

- **RESPOND:** Manage and analyze the incident, communicate about it, contain it, and eradicate the threat.
- **RECOVER:** Restore affected assets and services and support recovery from the incident.

For example, isolating a compromised workstation is a containment action under RESPOND. Restoring the workstation and validating its return to normal operation are recovery-related activities.

---

## 5. Key SOC Principles

- An alert is not automatically a confirmed incident.
- Prioritize according to evidence, organizational criteria, asset criticality, scope, and impact.
- Correlate logs to build a reliable timeline.
- Distinguish confirmed findings from hypotheses.
- Preserve evidence and document investigative actions.
- Follow the incident response plan and escalation procedures.
- Carry out containment and eradication actions only within the appropriate authorization.
- Communicate relevant information to designated stakeholders.
- Avoid claiming that suspicious activity proves a specific outcome without supporting evidence.

## 6. Interview Questions to Practise

1. What is the purpose of the NIST CSF 2.0 RESPOND Function?
2. What are the four RESPOND categories?
3. What is the difference between incident management and incident analysis?
4. What information should be included in an incident report?
5. What is the difference between containment and eradication?
6. How would you respond to a confirmed compromised account?
7. Why should a SOC analyst follow an incident response playbook?
8. What is the difference between RESPOND and RECOVER?

## 7. What I Learned Today

- RESPOND consists of Incident Management, Incident Analysis, Incident Response Reporting and Communication, and Incident Mitigation.
- Incident management includes prioritization, coordination, documentation, and escalation.
- Incident analysis correlates evidence to understand the timeline, affected assets, likely cause, scope, and impact.
- Communication should reach the appropriate stakeholders and distinguish verified findings from unconfirmed assumptions.
- Mitigation focuses on containment and eradication.
- Actions must follow the organization's response plan and authorization procedures.

## References

- **NIST Cybersecurity Framework (CSF) 2.0 — CSWP 29:**  
  https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.29.pdf
- **NIST Cybersecurity Framework:**  
  https://www.nist.gov/cyberframework

**Status:** Day 5 — RESPOND completed.
