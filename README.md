## 🎯 Repository Objective

This repository documents my structured learning of **NIST CSF 2.0** and its practical application to cybersecurity operations.

The learning approach is:

```text
Learn the Framework
        ↓
Understand the Concept
        ↓
Apply it to a Security Scenario
        ↓
Map it to SOC Activities
        ↓
Practice Interview Questions
        ↓
Document the Learning

The focus is on building practical understanding rather than only memorizing framework terminology.

🛡️ What is NIST CSF 2.0?
The NIST Cybersecurity Framework (CSF) 2.0 is a cybersecurity risk-management framework developed by the National Institute of Standards and Technology (NIST).

It provides a structured way for organizations to understand, assess, prioritize, and communicate cybersecurity risks.

CSF 2.0 is organized around six Functions:

Govern

Identify

Protect

Detect

Respond

Recover

These Functions provide a high-level structure for organizing cybersecurity risk-management activities.

🔄 The Six NIST CSF 2.0 Functions

┌─────────────┐
                    │    GOVERN   │
                    │ Risk Strategy│
                    └──────┬──────┘
                           ↓
                    ┌─────────────┐
                    │   IDENTIFY  │
                    │ Assets/Risk │
                    └──────┬──────┘
                           ↓
                    ┌─────────────┐
                    │   PROTECT   │
                    │ Safeguards  │
                    └──────┬──────┘
                           ↓
                    ┌─────────────┐
                    │    DETECT   │
                    │ Find Events │
                    └──────┬──────┘
                           ↓
                    ┌─────────────┐
                    │   RESPOND   │
                    │ Take Action │
                    └──────┬──────┘
                           ↓
                    ┌─────────────┐
                    │   RECOVER   │
                    │ Restore &   │
                    │ Improve     │
                    └─────────────┘
Important: The six Functions should not be treated as a strict linear incident-response process. They represent concurrent and continuous aspects of cybersecurity risk management.

🧑‍💻 SOC Analyst Perspective
A major objective of this repository is understanding how NIST CSF relates to the daily responsibilities of a SOC Analyst.

Detect
SOC activities include:

Monitoring SIEM alerts

Analyzing network traffic

Investigating endpoint alerts

Reviewing authentication logs

Correlating security events

Identifying suspicious behavior

Determining whether an event requires escalation

Respond
SOC activities may include:

Investigating security incidents

Determining scope and impact

Collecting evidence

Containing affected systems

Escalating incidents

Blocking malicious indicators

Documenting investigations

Although Detect and Respond are particularly relevant to SOC operations, understanding all six Functions is important because SOC activities exist within the organization's broader cybersecurity risk-management process.

🔬 Connection to My Existing Security Work
This repository will also connect NIST CSF concepts with practical cybersecurity investigations and projects.

Examples include:

Network Traffic Investigation
Using Wireshark and public PCAPs to investigate:

Port scanning

Network reconnaissance

Suspicious communication

Protocol-level anomalies

Potential command-and-control traffic

These investigations primarily relate to the Detect and Respond Functions.

Security Monitoring
Connecting NIST concepts with:

SIEM

Log analysis

Detection engineering

Network monitoring

Endpoint telemetry

Incident Investigation
Using realistic scenarios to practice:
Alert
  ↓
Validate
  ↓
Investigate
  ↓
Collect Evidence
  ↓
Determine Scope
  ↓
Contain
  ↓
Remediate
  ↓
Recover
  ↓
Lessons Learned

🧪 Practical Exercises
Each learning section may contain:

Concept summary

Practical cybersecurity scenario

NIST CSF mapping

SOC analyst perspective

Investigation workflow

Interview questions

Key takeaways

References

The objective is to create evidence of practical understanding, not simply collect theoretical notes.

📖 References
The primary references for this repository are official NIST resources.

NIST Cybersecurity Framework

https://www.nist.gov/cyberframework

NIST CSF 2.0 — Resource & Overview Guide

https://csrc.nist.gov/pubs/sp/1299/final

NIST CSF 2.0 — Full Framework

https://csrc.nist.gov/pubs/cswp/29/final

NIST CSF 2.0 — Quick-Start Guides

https://www.nist.gov/cyberframework/quick-start-guides

NIST CSF 2.0 — Frequently Asked Questions

https://www.nist.gov/cyberframework/faqs

NIST CSF Function Glossary

https://csrc.nist.gov/glossary/term/csf_function

NIST CSF 2.0 — Organizational Profiles

https://csrc.nist.gov/pubs/sp/1301/final

NIST CSF 2.0 — Tiers

https://csrc.nist.gov/pubs/sp/1302/final

⚠️ Disclaimer
This repository represents a personal learning and practical cybersecurity exercise.

The scenarios, mappings, and investigations documented here are intended for educational purposes and should not be interpreted as formal NIST compliance assessments or professional security assessments.

NIST CSF provides a framework for managing cybersecurity risk; organizations should adapt its implementation to their specific business, technology, regulatory, and risk environment.

🚀 Goal
The final objective of this repository is to build practical understanding of how a cybersecurity framework connects:

Business Risk
      ↓
Cybersecurity Risk
      ↓
Security Controls
      ↓
Security Monitoring
      ↓
Detection
      ↓
Incident Response
      ↓
Recovery
      ↓
Continuous Improvement
