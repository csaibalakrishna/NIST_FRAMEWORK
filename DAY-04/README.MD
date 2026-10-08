# Day 4 — NIST CSF 2.0: DETECT

## Objective

Understand the **DETECT (DE)** Function of the NIST Cybersecurity Framework (CSF) 2.0 and apply its concepts to a practical SOC investigation.

This day's learning was based primarily on the official:

**NIST Cybersecurity Framework (CSF) 2.0 — CSWP 29**

The focus was on understanding how organizations monitor for cybersecurity events, analyze security events, and maintain effective detection processes.

---

## 1. Understanding DETECT

The **DETECT** Function focuses on finding and analyzing possible cybersecurity attacks and compromises.

From a SOC perspective, DETECT answers:

> **How do we identify that potentially harmful cybersecurity activity is occurring?**

Detection is not simply generating an alert.

A SOC analyst must analyze available evidence and determine whether the activity is significant enough to require further investigation or incident response.

---

## 2. DETECT Structure

The DETECT Function contains three Categories:

```text
DETECT (DE)
│
├── DE.CM
│   └── Continuous Monitoring
│
├── DE.AE
│   └── Adverse Event Analysis
│
└── DE.DP
    └── Detection Process
```

---

## 3. DE.CM — Continuous Monitoring

### What it means

Continuous Monitoring focuses on monitoring systems, networks, and other relevant sources for potentially adverse cybersecurity events.

From a SOC perspective, monitoring can involve:

- Authentication logs
- Network traffic
- Endpoint telemetry
- SIEM data
- IDS/IPS alerts
- Security events
- Process activity
- External service activity

### Example

For suspicious authentication activity, a SOC may monitor:

```text
Failed Login Attempts
        ↓
Successful Login
        ↓
Source IP
        ↓
Login Time
        ↓
Endpoint Activity
```

The purpose is to identify unusual patterns that may require further analysis.

---

## 4. DE.AE — Adverse Event Analysis

### What it means

Adverse Event Analysis focuses on analyzing detected events and understanding their significance.

A SOC analyst should not automatically assume that every alert represents a confirmed security incident.

Instead, the analyst should:

1. Collect relevant evidence
2. Correlate events
3. Build a timeline
4. Identify affected users and systems
5. Analyze associated processes and network activity
6. Determine whether the activity is suspicious
7. Assess its potential significance

### SOC Investigation Example

Suppose the SIEM generates:

```text
10:02 — 15 failed login attempts
10:04 — Successful login
10:05 — Login from an unusual IP
10:07 — PowerShell process starts
10:09 — Large outbound connection
```

The analyst can correlate these events to determine whether they are related.

A simplified investigation timeline:

```text
Failed Logins
     ↓
Successful Login
     ↓
Unusual Source IP
     ↓
PowerShell Execution
     ↓
Outbound Network Connection
     ↓
Correlate Events
     ↓
Investigate
     ↓
Determine Significance
```

---

## 5. Using Splunk for Event Correlation

SIEM platforms such as Splunk can be used to correlate events across different data sources.

An analyst may investigate:

- Username
- Source IP
- Destination IP
- Login time
- Hostname
- Process execution
- Network connections
- Authentication events

For example, the analyst could use Splunk to build a timeline around a suspicious login and determine what activity occurred before and after the authentication event.

The objective is not simply to find an alert, but to understand the sequence of activity.

---

## 6. DE.DP — Detection Process

### What it means

Detection processes provide a structured way for an organization to perform and maintain cybersecurity detection activities.

From a SOC perspective, this involves:

- Maintaining detection capabilities
- Validating suspicious activity
- Documenting findings
- Communicating significant events
- Escalating according to organizational procedures
- Improving detection capabilities based on lessons learned

---

## 7. Practical SOC Detection Workflow

A practical detection workflow can be represented as:

```text
Security Event
      ↓
Alert
      ↓
Triage
      ↓
Correlation
      ↓
Investigation
      ↓
Evidence Collection
      ↓
Determine Significance
      ↓
Incident Criteria Met?
      │
      ├── No → Close / Monitor
      │
      └── Yes
            ↓
       Document
            ↓
       Escalate
```

The exact workflow and escalation criteria depend on the organization's procedures.

---

## 8. Practical Scenario

### Scenario

A SIEM generates the following events for an employee account:

```text
10:02 — 15 failed login attempts
10:04 — Successful login
10:05 — Login originates from an unusual IP
10:07 — PowerShell process starts on the user's workstation
10:09 — Large outbound connection to an external IP
```

The activity is investigated using the three DETECT Categories.

### DE.CM — Continuous Monitoring

The SOC monitors:

- Authentication logs
- Source IP addresses
- Successful and failed logins
- Endpoint telemetry
- Process execution
- Network connections
- SIEM events

The objective is to identify unusual activity.

### DE.AE — Adverse Event Analysis

The analyst correlates the events using the SIEM.

The investigation may determine:

- Which user authenticated
- Which workstation was involved
- Where the login originated
- Whether the IP is unusual or suspicious
- What processes executed after the login
- What network connections occurred afterward
- Whether the events are related

The analyst builds a timeline to understand the activity.

### DE.DP — Detection Process

If the activity is sufficiently validated as suspicious:

- Document the investigation
- Record relevant evidence
- Record the event timeline
- Determine scope and potential impact
- Follow the organization's escalation procedure
- Assign severity according to established criteria
- Escalate when required

The incident should not automatically be classified as high risk simply because suspicious activity was observed.

Severity should be based on evidence, asset criticality, potential impact, and organizational incident-classification criteria.

---

## 9. Important SOC Concept

### Alert ≠ Incident

One of the key lessons from today's exercise is that a security alert does not automatically mean that an incident has occurred.

A better way to think about the process is:

```text
Event
  ↓
Alert
  ↓
Triage
  ↓
Correlation
  ↓
Investigation
  ↓
Evidence
  ↓
Determine Significance
  ↓
Security Incident
```

The SOC analyst's responsibility is to determine what the available evidence actually indicates.

---

## 10. Evidence-Based Detection

Detection decisions should be based on evidence.

For example, if a user has:

```text
Multiple failed logins
        +
Successful login
        +
Unusual source IP
        +
PowerShell execution
        +
Large outbound connection
```

the combination is more significant than any individual event by itself.

This demonstrates why event correlation and context are important in SOC operations.

---

## 11. Connection Between Previous Days and DETECT

The relationship between the Functions studied so far can be understood as:

```text
GOVERN
How should cybersecurity risk be managed?
        ↓
IDENTIFY
What assets and risks exist?
        ↓
PROTECT
What safeguards should be implemented?
        ↓
DETECT
How do we know suspicious activity is occurring?
```

Example:

```text
IDENTIFY
Critical workstation
        ↓
PROTECT
MFA + EDR + Least Privilege
        ↓
DETECT
Suspicious login + PowerShell + Network activity
```

---

## 12. SOC Tools Related to DETECT

Detection activities can involve multiple security technologies.

### SIEM

Used for:

- Log collection
- Event correlation
- Alerting
- Timeline analysis
- Investigation

Examples:

- Splunk
- Microsoft Sentinel
- IBM QRadar

### EDR

Used for:

- Endpoint telemetry
- Process monitoring
- Suspicious behavior detection
- Endpoint investigation

### Network Monitoring

Used for:

- Network traffic analysis
- Suspicious connections
- Port scanning
- C2 indicators
- Anomalous communication

Examples:

- Wireshark
- IDS/IPS
- Network detection tools

The tool is less important than understanding the detection process and evidence produced by it.

---

## 13. Key Learning

### DE.CM — Continuous Monitoring

Think:

What are we continuously watching?

Examples:

- Authentication
- Endpoints
- Network traffic
- Security logs
- Processes

### DE.AE — Adverse Event Analysis

Think:

What does this activity actually mean?

Examples:

- Correlate events
- Build timelines
- Investigate users
- Analyze processes
- Examine network activity
- Determine significance

### DE.DP — Detection Process

Think:

How does the organization consistently detect, document, communicate, and improve detection activities?

Examples:

- Maintain detection processes
- Validate findings
- Document evidence
- Escalate significant events
- Improve detection capabilities

---

## 14. Interview Takeaways

### Q1. What is the DETECT Function in NIST CSF 2.0?

The DETECT Function focuses on finding and analyzing possible cybersecurity attacks and compromises through continuous monitoring, adverse event analysis, and effective detection processes.

### Q2. What are the three DETECT Categories?

Continuous Monitoring (DE.CM), Adverse Event Analysis (DE.AE), and Detection Process (DE.DP).

### Q3. How would a SOC analyst investigate multiple failed logins followed by a successful login?

I would correlate the authentication events with the username, source IP, destination system, timing, endpoint activity, and other relevant telemetry. I would then investigate what happened after the successful login and determine whether the activity represents suspicious or malicious behavior.

### Q4. Does a SIEM alert automatically mean there is an incident?

No. An alert is an indication that requires triage and investigation. The analyst needs to validate and correlate the available evidence before determining whether an incident has occurred.

### Q5. How can Splunk support the DETECT Function?

Splunk can collect and correlate security events from multiple sources, allowing analysts to build timelines, investigate suspicious activity, identify patterns, and support detection and incident triage.

### Q6. Should every suspicious alert automatically be classified as high risk?

No. Severity should be determined using evidence, asset criticality, potential impact, scope, and the organization's incident-classification criteria.

---

## 15. What I Learned Today

- DETECT focuses on finding and analyzing possible cybersecurity attacks and compromises.
- DETECT has three Categories:
  - Continuous Monitoring
  - Adverse Event Analysis
  - Detection Process
- SOC analysts use logs, SIEM, endpoint telemetry, and network data to detect suspicious activity.
- Event correlation provides context that individual alerts may not provide.
- Splunk can be used to correlate authentication, endpoint, and network events.
- Building a timeline helps analysts understand the sequence of activity.
- A security alert does not automatically mean a confirmed security incident.
- Detection should be evidence-based.
- Severity should not automatically be classified as high without sufficient evidence.
- SOC analysts should document and escalate validated suspicious activity according to organizational procedures.
- Detection findings can contribute to improving an organization's overall detection capabilities.

---

## Reference

### Primary Source

NIST Cybersecurity Framework (CSF) 2.0 — CSWP 29
National Institute of Standards and Technology (NIST)

<https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.29.pdf>

### Relevant Sections

- Section 2 — CSF Core
- Appendix A — CSF Core
- DETECT (DE)
- DE.CM — Continuous Monitoring
- DE.AE — Adverse Event Analysis
- DE.DP — Detection Process

### Official NIST CSF Website

<https://www.nist.gov/cyberframework>
