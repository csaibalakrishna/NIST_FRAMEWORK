# Day 2 — NIST CSF 2.0: GOVERN & IDENTIFY

## Objective

Understand the **GOVERN** and **IDENTIFY** Functions of the NIST Cybersecurity Framework (CSF) 2.0 and apply their concepts to a practical cybersecurity scenario from a SOC / Blue Team perspective.

This day's learning was based primarily on the official **NIST Cybersecurity Framework (CSF) 2.0 — CSWP 29**.

---

## 1. Understanding the CSF Core

The NIST CSF 2.0 Core is organized into three levels:

```text
FUNCTION
   ↓
CATEGORY
   ↓
SUBCATEGORY
```

### Function

A Function organizes cybersecurity outcomes at the highest level.

CSF 2.0 contains six Functions:

1. GOVERN
2. IDENTIFY
3. PROTECT
4. DETECT
5. RESPOND
6. RECOVER

### Category

Categories group related cybersecurity outcomes within a Function.

### Subcategory

Subcategories provide more specific outcomes within each Category.

The CSF Core is a taxonomy of cybersecurity outcomes. It does not prescribe one specific way an organization must achieve those outcomes.

---

## 2. GOVERN (GV)

### Definition

The GOVERN Function establishes, communicates, and monitors the organization's:

- Cybersecurity risk management strategy
- Expectations
- Policies

GOVERN also helps inform and prioritize the outcomes of the other five Functions based on the organization's mission and stakeholder expectations.

It incorporates cybersecurity into the organization's broader Enterprise Risk Management (ERM) strategy.

### Why GOVERN is Important

Governance provides the direction for how an organization manages cybersecurity risk.

It answers questions such as:

- What cybersecurity risks does the organization need to manage?
- What is the organization's cybersecurity strategy?
- Who is responsible for cybersecurity decisions?
- What policies and expectations exist?
- How is cybersecurity risk communicated and monitored?
- How should cybersecurity risk align with business objectives?

---

## 3. GOVERN Structure

The GOVERN Function contains the following Categories:

```text
GOVERN (GV)
│
├── GV.OC
│   └── Organizational Context
│
├── GV.RM
│   └── Risk Management Strategy
│
├── GV.RR
│   └── Roles, Responsibilities, and Authorities
│
├── GV.PO
│   └── Policy
│
├── GV.OV
│   └── Oversight
│
└── GV.SC
    └── Cybersecurity Supply Chain Risk Management
```

### GV.OC — Organizational Context

Focuses on understanding the organization's circumstances and context that affect cybersecurity risk management.

This includes understanding:

- Organizational mission
- Stakeholders
- Legal and regulatory requirements
- Business objectives
- Dependencies
- Internal and external factors affecting cybersecurity

**SOC Perspective**

A SOC analyst should understand that security events need to be considered in the context of the organization's environment.

For example:

The same suspicious connection could have very different consequences depending on whether the affected system is a normal employee workstation or a system supporting a critical business function.

### GV.RM — Risk Management Strategy

Focuses on establishing and communicating the organization's cybersecurity risk management strategy.

This includes understanding how the organization approaches:

- Cybersecurity risk
- Risk priorities
- Risk appetite and tolerance
- Risk response
- Alignment with enterprise risk management

**SOC Perspective**

A SOC does not investigate every alert in exactly the same way.

Risk management helps determine:

- What should be prioritized?
- Which assets are most important?
- Which incidents require immediate escalation?
- What level of risk is acceptable?

### GV.RR — Roles, Responsibilities, and Authorities

Focuses on defining and communicating cybersecurity roles, responsibilities, and authorities.

This helps establish:

- Who is responsible for cybersecurity decisions
- Who investigates incidents
- Who has authority to take response actions
- Who receives escalations
- How responsibilities are distributed

**SOC Example**

A simplified incident workflow could involve:

```text
Security Alert
      ↓
SOC Analyst
      ↓
Investigation
      ↓
SOC Lead / Incident Response
      ↓
Escalation / Response Decision
```

The exact responsibilities depend on the organization's structure.

### GV.PO — Policy

Focuses on establishing, communicating, enforcing, and maintaining cybersecurity policies.

Examples include policies related to:

- Access control
- Network security
- Incident response
- Data protection
- Acceptable use
- Security monitoring

**SOC Perspective**

If suspicious network communication is detected, the SOC should follow the organization's defined policies and procedures rather than responding inconsistently.

### GV.OV — Oversight

Focuses on reviewing and adjusting the organization's cybersecurity risk management strategy and activities.

Oversight helps determine whether cybersecurity risk management is working as intended and whether changes are required.

**SOC Perspective**

Security operations should not remain static.

Findings from incidents, investigations, and security monitoring can identify areas where policies, processes, or security capabilities need improvement.

### GV.SC — Cybersecurity Supply Chain Risk Management

Focuses on cybersecurity risks associated with suppliers and third parties.

Organizations may depend on:

- Cloud providers
- Software vendors
- Managed security providers
- Hardware suppliers
- External service providers

These relationships can introduce cybersecurity risks that need to be managed.

---

## 4. IDENTIFY (ID)

### Definition

The IDENTIFY Function focuses on understanding the organization's current cybersecurity risks.

This includes understanding:

- Assets
- Suppliers
- Cybersecurity risks
- Dependencies
- Potential impacts

Understanding these factors helps the organization prioritize cybersecurity efforts according to its risk management strategy and mission requirements.

IDENTIFY also includes identifying opportunities to improve policies, plans, processes, procedures, and practices supporting cybersecurity risk management.

---

## 5. IDENTIFY Structure

The IDENTIFY Function contains the following Categories:

```text
IDENTIFY (ID)
│
├── ID.AM
│   └── Asset Management
│
├── ID.RA
│   └── Risk Assessment
│
└── ID.IM
    └── Improvement
```

### ID.AM — Asset Management

Asset Management focuses on understanding and managing organizational assets.

Assets can include:

- Data
- Hardware
- Software
- Systems
- Facilities
- Services
- People
- Suppliers

**SOC Perspective**

Before investigating a security alert, understanding the affected asset is important.

For example:

```text
Security Alert
      ↓
Identify affected asset
      ↓
Who owns it?
      ↓
What is it used for?
      ↓
What data does it handle?
      ↓
How critical is it?
      ↓
What risks could affect it?
```

### ID.RA — Risk Assessment

Risk Assessment focuses on understanding cybersecurity risks affecting the organization.

This requires considering:

- Threats
- Vulnerabilities
- Likelihood
- Potential impact
- Asset criticality
- Business context

**SOC Perspective**

A suspicious event should not automatically be classified as a confirmed high-risk incident.

The analyst should gather evidence and determine:

- What happened?
- Which asset is affected?
- Is the activity malicious?
- Is the asset compromised?
- What data could be affected?
- Is there evidence of lateral movement?
- What could be the business impact?

Risk and severity should be determined using the organization's risk-management and incident-triage processes.

### ID.IM — Improvement

Improvement focuses on identifying opportunities to improve cybersecurity risk management.

Lessons from:

- Security incidents
- Assessments
- Monitoring
- Investigations
- Testing
- Operational experience

can be used to improve cybersecurity policies, processes, procedures, and practices.

**SOC Perspective**

An incident investigation should not necessarily end when the immediate threat is contained.

The organization can ask:

What can we improve so that a similar incident is less likely to occur or is detected earlier?

---

## 6. Practical SOC Scenario

### Scenario

A company has:

- 500 employee laptops
- 20 servers
- Active Directory
- VPN
- Firewall
- Cloud applications
- SIEM

The SOC receives an alert that an employee workstation is communicating with an unknown external IP address.

### GOVERN Analysis

#### 1. Policy

Review the organization's:

- Network security policy
- Incident response policy
- Security monitoring procedures
- Escalation procedures

to determine how suspicious external communication should be handled.

#### 2. Responsibility

Determine who is responsible for:

- Alert investigation
- Incident escalation
- Containment
- Incident response decisions

For example:

```text
Employee
   ↓
Provides contextual information
   ↓
SOC Analyst
   ↓
Investigates
   ↓
SOC Lead / Incident Response
   ↓
Escalation and response decisions
```

#### 3. Risk Management

Do not immediately assume that the event is low, medium, or high risk without sufficient evidence.

First determine:

- Whether the external IP is legitimate
- Whether the workstation is compromised
- Whether credentials were compromised
- Whether data was accessed or exfiltrated
- Whether lateral movement occurred
- How critical the affected asset is
- What the potential business impact is

### IDENTIFY Analysis

#### 1. Assets

**Known asset**

- Employee workstation

**Potentially affected assets**

If evidence of lateral movement is discovered:

- Other endpoints
- Internal servers
- User accounts
- Network resources

These should be treated as potential assets requiring investigation rather than assumed to be compromised.

#### 2. Information to Collect About the Workstation

Potential investigation data includes:

- Hostname
- Username
- IP address
- Operating system
- Endpoint logs
- EDR telemetry
- Running processes
- Network connections
- Authentication activity
- Commands or processes executed
- Relevant security events

If the investigation warrants deeper analysis, memory forensics may also be considered.

#### 3. Investigating the External IP

The external IP can be investigated using:

- Threat intelligence
- IP reputation
- WHOIS / ownership information
- DNS history
- Previous sightings
- Organization's internal history
- Connection frequency
- Destination ports
- Protocols
- VPN / proxy / other connection context

The objective is to determine whether the communication is:

```text
Legitimate
   OR
Suspicious
   OR
Known Malicious
```

#### 4. Potential Risks

The suspicious communication could potentially indicate:

- Command and Control (C2)
- Data exfiltration
- Credential compromise
- Lateral movement
- Persistence
- Unauthorized access
- Malware communication
- Backdoor activity

These are potential risks, not confirmed findings.

Evidence is required before concluding that a workstation is compromised or participating in C2.

#### 5. Determining Asset Criticality

Asset criticality should not be determined only by the employee's job position.

Factors can include:

- Business function
- Data handled
- User privileges
- System dependencies
- Connectivity to critical systems
- Business impact if unavailable
- Sensitivity of information
- Number of users or services depending on the system

For example:

A normal employee workstation supporting a critical business process could be more important than a highly privileged workstation with limited business impact.

---

## Key Learning

### GOVERN

Think:

How does the organization manage cybersecurity risk?

```text
Organizational Context
        ↓
Risk Management Strategy
        ↓
Roles & Responsibilities
        ↓
Policies
        ↓
Oversight
        ↓
Supply Chain Risk Management
```

### IDENTIFY

Think:

What assets and cybersecurity risks does the organization have?

```text
Assets
  ↓
Business Context
  ↓
Threats & Vulnerabilities
  ↓
Risk Assessment
  ↓
Potential Impact
  ↓
Prioritization
  ↓
Improvement
```

---

## Important NIST CSF Concept

The CSF Functions are not a strict linear sequence.

NIST states that the Functions should be addressed concurrently.

```text
GOVERN
   ↕
IDENTIFY
   ↕
PROTECT
   ↕
DETECT
   ↕
RESPOND
   ↕
RECOVER
```

GOVERN, IDENTIFY, PROTECT, and DETECT activities occur continuously, while RESPOND and RECOVER activities should be ready and occur when cybersecurity incidents happen.

GOVERN is especially important because it informs how the organization implements the other Functions.

---

## SOC Analyst Takeaways

From a SOC perspective:

### GOVERN

Understand:

- Security policies
- Roles and responsibilities
- Escalation procedures
- Risk-management strategy
- Organizational context

### IDENTIFY

Understand:

- What asset is affected?
- Who owns it?
- What is it used for?
- How critical is it?
- What data does it handle?
- What risks affect it?
- What could be the business impact?

---

## Interview Questions Practiced

### Q1. What is the GOVERN Function?

GOVERN establishes, communicates, and monitors the organization's cybersecurity risk management strategy, expectations, and policy. It also provides direction for the other CSF Functions and integrates cybersecurity into broader enterprise risk management.

### Q2. What is the IDENTIFY Function?

IDENTIFY focuses on understanding the organization's current cybersecurity risks by understanding assets, suppliers, and related risks, while also identifying opportunities for improvement.

### Q3. How would you apply IDENTIFY during a SOC investigation?

I would first identify the affected asset, its owner, purpose, criticality, associated data, dependencies, and relevant risks. I would then use that context to understand the potential impact and prioritize the investigation.

### Q4. If a workstation communicates with an unknown external IP, would you immediately classify it as high risk?

No. I would investigate the IP, affected asset, connection details, endpoint activity, user context, and potential impact before assigning a final risk or severity. The initial alert can be prioritized according to the organization's triage process, but the final risk assessment should be evidence-based.

### Q5. Why is asset identification important?

Understanding assets allows an organization to understand what needs protection, what risks affect those assets, and how cybersecurity efforts should be prioritized based on business and mission requirements.

---

## What I Learned Today

- The NIST CSF Core is structured as Functions → Categories → Subcategories.
- GOVERN establishes and manages cybersecurity risk strategy, expectations, and policy.
- GOVERN incorporates cybersecurity into broader enterprise risk management.
- GOVERN includes organizational context, risk management strategy, roles and responsibilities, policy, oversight, and supply-chain risk management.
- IDENTIFY focuses on understanding current cybersecurity risks.
- IDENTIFY includes understanding assets, suppliers, and related cybersecurity risks.
- IDENTIFY contains Asset Management, Risk Assessment, and Improvement.
- Asset criticality depends on business context and potential impact, not simply the user's job title.
- Security alerts should not automatically be assigned a final risk level without sufficient evidence.
- Potential C2, data exfiltration, or lateral movement should be investigated and supported by evidence before being treated as confirmed findings.
- The six NIST CSF Functions are concurrent and interconnected rather than a strict linear process.

---

## Reference

### Primary Source

NIST Cybersecurity Framework (CSF) 2.0 — CSWP 29
National Institute of Standards and Technology (NIST)

<https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.29.pdf>

### Relevant Sections

- Section 2 — Introduction to the CSF Core
- Appendix A — CSF Core
- GOVERN (GV)
- IDENTIFY (ID)
