# Day 1 — NIST Cybersecurity Framework (CSF) 2.0

## Objective

Understand the fundamentals of the **NIST Cybersecurity Framework (CSF) 2.0** and learn how its six Functions can be applied to a practical cybersecurity incident from a SOC/Blue Team perspective.

---

## What is NIST CSF?

The **NIST Cybersecurity Framework (CSF) 2.0** is a cybersecurity risk-management framework that helps organizations understand, assess, prioritize, and communicate cybersecurity risks.

CSF 2.0 is organized into six high-level Functions:

1. **Govern**
2. **Identify**
3. **Protect**
4. **Detect**
5. **Respond**
6. **Recover**

These Functions provide a high-level structure for organizing cybersecurity outcomes across an organization.

---

# 1. Govern

### What it means

Establish and manage the organization's cybersecurity risk-management strategy, expectations, policies, and responsibilities.

### Examples

- Establish cybersecurity policies
- Define security responsibilities
- Establish risk-management strategy
- Define incident-response processes
- Manage cybersecurity supply-chain risk

### SOC perspective

Govern determines **how the organization is expected to manage cybersecurity risk**.

> Example: An organization has an incident-response policy defining how SOC analysts should escalate and handle security incidents.

---

# 2. Identify

### What it means

Understand the organization's assets, environment, cybersecurity risks, and potential impact.

### Examples

- Identify critical assets
- Maintain asset inventory
- Identify cybersecurity risks
- Understand business dependencies
- Assess vulnerabilities and potential impact

### SOC perspective

Before investigating an alert, analysts need to understand:

- What system is affected?
- Who owns it?
- How critical is it?
- What services does it provide?
- What risks are associated with it?

> Example: A suspicious connection originates from a workstation communicating with an internal server. The analyst identifies the systems involved and determines their importance to the organization.

---

# 3. Protect

### What it means

Implement safeguards to manage and reduce identified cybersecurity risks.

### Examples

- Identity and access management
- Multi-factor authentication
- Least privilege
- Security awareness training
- Endpoint protection
- Network security controls
- Secure configuration
- Data security

### SOC perspective

Protection focuses on **reducing the likelihood or impact of security incidents**.

> Example: EDR, firewall rules, IPS, MFA, and access controls can help protect systems against different attack scenarios.

---

# 4. Detect

### What it means

Find and analyze possible cybersecurity attacks, compromises, or other adverse events.

### Examples

- Continuous monitoring
- SIEM monitoring
- Network traffic analysis
- Endpoint monitoring
- Log analysis
- Detection rules
- Alert investigation
- Anomaly detection

### SOC perspective

This is one of the most directly relevant Functions for a SOC Analyst.

A SOC analyst may:

1. Receive an alert
2. Examine logs and network traffic
3. Identify suspicious behavior
4. Correlate events
5. Determine whether the activity represents a security event or incident

### Connection to my practical work

My Wireshark-based PCAP investigations primarily fall under **Detect**.

For example, during network traffic investigations, suspicious behaviors such as:

- TCP port scanning
- ACK-based reconnaissance
- Unusual network communication
- Suspicious HTTP traffic

can be identified through packet-level analysis.

---

# 5. Respond

### What it means

Take action after a cybersecurity incident has been detected.

### Examples

- Analyze the incident
- Contain affected systems
- Mitigate the threat
- Coordinate response activities
- Report the incident
- Preserve relevant evidence

### SOC perspective

A typical response could involve:

```text
Alert
  ↓
Validate
  ↓
Investigate
  ↓
Determine scope and impact
  ↓
Contain
  ↓
Escalate / Remediate
```

> Example: If a workstation is suspected of communicating with malicious infrastructure, the analyst may investigate the source and destination, check for signs of compromise or data exfiltration, and isolate the endpoint when appropriate.

---

# 6. Recover

### What it means

Restore systems, assets, and operations affected by a cybersecurity incident.

### Examples

- Restore affected systems
- Recover data
- Validate restored systems
- Return services to normal operation
- Communicate recovery status
- Capture lessons learned
- Improve security processes

### SOC perspective

Recovery is not simply restoring a backup.

The organization should also verify that:

- The threat has been removed
- Systems are secure
- Credentials have been addressed where necessary
- Vulnerabilities have been remediated
- Systems can safely return to production
- Lessons from the incident are incorporated into future improvements

---

# Practical Exercise

## Scenario

> A SOC receives an alert that a workstation is making thousands of outbound connections to different destination ports on an internal server.

The incident was mapped against the six NIST CSF 2.0 Functions.

| Function     | Practical application                                                                                                                         |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------- |
| **Govern**   | Ensure incident-response and network-security policies define how suspicious network activity should be handled.                              |
| **Identify** | Identify the affected workstation, destination server, assets involved, and associated risk.                                                  |
| **Protect**  | Use safeguards such as EDR, IPS, firewalls, and access controls to reduce risk.                                                               |
| **Detect**   | Use SIEM and network monitoring to identify abnormal outbound communication.                                                                  |
| **Respond**  | Investigate the source and destination, determine whether data exfiltration occurred, and isolate the workstation if compromise is suspected. |
| **Recover**  | Restore affected systems/data, verify that the threat has been removed, return systems to normal operation, and apply lessons learned.        |

---

# Key Learning

The six Functions can be remembered as:

```text
GOVERN
   ↓
How do we manage cybersecurity risk?

IDENTIFY
   ↓
What assets and risks do we have?

PROTECT
   ↓
What safeguards do we use?

DETECT
   ↓
How do we know something is happening?

RESPOND
   ↓
What do we do when something happens?

RECOVER
   ↓
How do we restore operations and improve?
```

### Important clarification

The Functions should **not** be treated as a strict step-by-step incident-response checklist.

NIST describes them as concurrent and continuous aspects of cybersecurity risk management. Govern, Identify, Protect, and Detect activities occur continuously, while Respond and Recover are ready and activated when incidents occur.

---

# SOC Analyst Relevance

For a SOC Analyst, the most immediately relevant Functions are:

### Detect

Analyzing:

- SIEM alerts
- Network traffic
- Endpoint telemetry
- Authentication logs
- Security events

### Respond

Performing:

- Alert investigation
- Incident analysis
- Containment
- Escalation
- Evidence collection
- Incident documentation

However, a SOC analyst should understand all six Functions because SOC operations exist within the organization's broader cybersecurity risk-management program.

---

# Interview Takeaway

> &#x20;to SOC operations. Detect involves identifying and analyzing possible cybersecurity evenQuestion: What is NIST CSF 2.0?
>
> **Answer:**
>
> > NIST CSF 2.0 is a cybersecurity risk-management framework that helps organizations understand, assess, prioritize, and communicate cybersecurity risks. It is organized around six Functions: Govern, Identify, Protect, Detect, Respond, and Recover.
>
> ### Question: Which NIST CSF function is most relevant to a SOC analyst?
>
> **Answer:**
>
> > Detect and Respond are particularly relevantts, while Respond involves taking action after an incident has been detected. However, SOC activities support the organization's broader CSF lifecycle.

---

# What I Learned Today

- NIST CSF 2.0 is a **risk-management framework**, not a SIEM or security tool.
- CSF 2.0 has **six Functions**.
- **Govern** establishes cybersecurity risk-management strategy, expectations, and policies.
- **Identify** focuses on understanding assets and cybersecurity risks.
- **Protect** focuses on safeguards.
- **Detect** focuses on identifying and analyzing possible cybersecurity events.
- **Respond** focuses on actions taken after detection.
- **Recover** focuses on restoring affected assets and operations.
- A SOC analyst's work is especially connected to **Detect and Respond**.
- The CSF Functions are **not simply a linear incident-response sequence**.
- Practical security investigations can be mapped to CSF outcomes to understand their role within a broader security program.

---

# References

### Official NIST Resources

1. **NIST Cybersecurity Framework 2.0 — Official Framework**

   - [https://www.nist.gov/cyberframework](https://www.nist.gov/cyberframework)

2. **NIST CSF 2.0 — Resource & Overview Guide (SP 1299)**

   - [https://csrc.nist.gov/pubs/sp/1299/final](https://csrc.nist.gov/pubs/sp/1299/final)

3. **NIST CSF 2.0 — Full Framework (CSWP 29)**

   - [https://csrc.nist.gov/pubs/cswp/29/final](https://csrc.nist.gov/pubs/cswp/29/final)

4. **NIST CSF 2.0 Quick-Start Guides**

   - [https://www.nist.gov/cyberframework/quick-start-guides](https://www.nist.gov/cyberframework/quick-start-guides)

5. **NIST CSF 2.0 FAQ**

   - [https://www.nist.gov/cyberframework/faqs](https://www.nist.gov/cyberframework/faqs)

6. **NIST CSF Function Glossary**

   - [https://csrc.nist.gov/glossary/term/csf_function](https://csrc.nist.gov/glossary/term/csf_function)

7. **NIST CSF 2.0 — Organizational Profiles (SP 1301)**

   - [https://csrc.nist.gov/pubs/sp/1301/final](https://csrc.nist.gov/pubs/sp/1301/final)

8. **NIST CSF 2.0 — Tiers (SP 1302)**

   - [https://csrc.nist.gov/pubs/sp/1302/final](https://csrc.nist.gov/pubs/sp/1302/final)

---

## Official Reference

**National Institute of Standards and Technology (NIST)**
Cybersecurity Framework 2.0

[https://www.nist.gov/cyberframework](https://www.nist.gov/cyberframework)

---

## Status

**Day 1 — Completed**

Focus:

- NIST CSF 2.0 fundamentals
- Six Functions
- SOC relevance
- Practical incident mapping
- Interview preparation
