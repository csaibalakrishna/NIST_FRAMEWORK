# Day 3 — NIST CSF 2.0: PROTECT

## Objective

Understand the **PROTECT (PR)** Function of the NIST Cybersecurity Framework (CSF) 2.0 and apply its concepts to a practical cybersecurity scenario from a SOC / Blue Team perspective.

This day's learning was based primarily on the official:

**NIST Cybersecurity Framework (CSF) 2.0 — CSWP 29**

---

## 1. Understanding PROTECT

The **PROTECT** Function focuses on using safeguards to manage cybersecurity risks.

The purpose of PROTECT is to help organizations appropriately safeguard assets and reduce cybersecurity risk based on the organization's risk management strategy.

From a practical security perspective, PROTECT answers:

> **What safeguards can we implement to reduce cybersecurity risk?**

---

## 2. PROTECT Structure

The PROTECT Function contains the following Categories:

```text
PROTECT (PR)
│
├── PR.AA
│   └── Identity Management, Authentication, and Access Control
│
├── PR.AT
│   └── Awareness and Training
│
├── PR.DS
│   └── Data Security
│
├── PR.PS
│   └── Platform Security
│
└── PR.IR
    └── Technology Infrastructure Resilience
```

---

## 3. PR.AA — Identity Management, Authentication, and Access Control

This Category focuses on managing identities, authenticating users and entities, and controlling access to resources.

### Practical Security Controls

Examples include:

- Strong authentication
- Multi-factor authentication (MFA)
- Least privilege
- Role-based access control
- Removing unnecessary administrative privileges
- Access management

### SOC Perspective

If users have excessive privileges or weak authentication, an attacker who compromises an account may gain unnecessary access to organizational resources.

For example:

```text
Compromised Account
        ↓
Weak Authentication
        ↓
Excessive Privileges
        ↓
Unauthorized Access
        ↓
Potential Lateral Movement
```

Controls such as MFA and least privilege can reduce this risk.

---

## 4. PR.AT — Awareness and Training

This Category focuses on providing cybersecurity awareness and training to users and relevant personnel.

### Practical Examples

Employees should understand:

- How to identify phishing
- How to recognize suspicious links
- How to identify suspicious attachments
- Why passwords should not be shared
- How to report suspicious activity
- Basic organizational security procedures

### SOC Perspective

Security awareness can reduce the likelihood of successful social-engineering attacks.

For example:

```text
Phishing Email
      ↓
Employee Recognizes Suspicious Link
      ↓
Does Not Click
      ↓
Reports Email
      ↓
SOC Investigation
```

---

## 5. PR.DS — Data Security

This Category focuses on protecting data in accordance with the organization's risk strategy.

### Practical Security Controls

Examples include:

- Encryption at rest
- Encryption in transit
- Access controls
- Data protection mechanisms
- Appropriate backups
- Data handling policies

### Important Technical Distinction

Encryption and hashing serve different purposes.

#### Encryption

Used to protect data so that authorized parties can recover the original information.

Examples:

- Disk/database encryption
- TLS for data in transit

#### Hashing

Generally used for purposes such as:

- Password verification
- Integrity checking

Hashing should not be described as a general replacement for encryption when protecting sensitive data.

---

## 6. PR.PS — Platform Security

This Category focuses on protecting the platforms that support organizational services.

Platforms may include:

- Operating systems
- Applications
- Servers
- Endpoints
- Network devices
- Other technology platforms

### Practical Security Measures

Examples include:

- Applying security patches
- Keeping software updated
- Secure configuration
- Removing unnecessary privileges
- Endpoint protection
- Vulnerability management
- Security testing

### SOC Perspective

Outdated software can increase the attack surface of an organization.

A security team should therefore:

```text
Identify Vulnerable Software
        ↓
Assess Risk
        ↓
Prioritize
        ↓
Patch / Mitigate
        ↓
Verify
```

---

## 7. PR.IR — Technology Infrastructure Resilience

This Category focuses on the resilience of technology infrastructure.

The objective is to help technology infrastructure remain available and resilient against adverse events.

### Practical Examples

- Redundant systems
- Network redundancy
- Failover mechanisms
- Backup infrastructure
- Resilient architecture
- Recovery capabilities
- Capacity planning

### SOC Perspective

Security is not only about preventing attacks.

Organizations also need to maintain or restore critical services when security incidents or other disruptions occur.

---

## 8. Practical Scenario

### Scenario

A company discovers that:

- Several employees have weak passwords
- Some employees have local administrator privileges
- Important software is outdated
- VPN accounts do not use MFA

The situation was analyzed using the PROTECT Function.

### PR.AA — Identity Management, Authentication, and Access Control

#### Problem

- Weak passwords
- Excessive administrator privileges
- No MFA for VPN accounts

#### Recommended safeguards

- Strong authentication
- MFA
- Least privilege
- Remove unnecessary administrator privileges
- Role-based access where appropriate

#### Expected benefit

Reduce the likelihood that compromised credentials can be used to gain unauthorized access or move further through the environment.

### PR.AT — Awareness and Training

#### Problem

Employees may be susceptible to:

- Phishing
- Malicious links
- Credential theft
- Unsafe security practices

#### Recommended safeguards

Provide security awareness training covering:

- Phishing identification
- Suspicious links and attachments
- Credential protection
- Password security
- Incident reporting

### PR.DS — Data Security

#### Recommended safeguards

Protect sensitive data using:

- Encryption at rest
- TLS for data in transit
- Appropriate access controls
- Backups
- Data protection policies

The controls should be selected according to the organization's risk and data requirements.

### PR.PS — Platform Security

#### Problem

The company is running outdated software and some users have unnecessary administrative privileges.

#### Recommended safeguards

- Patch outdated software
- Maintain supported software versions
- Securely configure systems
- Remove unnecessary administrator privileges
- Use endpoint security controls
- Perform vulnerability management and security testing where appropriate

### PR.IR — Technology Infrastructure Resilience

#### Problem

A security incident could disrupt business operations.

#### Recommended safeguards

- Redundant infrastructure
- Network resilience
- Backup systems
- Failover mechanisms
- Recovery capabilities
- Resilient architecture

The goal is to reduce the impact of disruptions and maintain important business operations.

---

## 9. SOC Analyst Perspective

PROTECT is primarily about reducing cybersecurity risk through safeguards.

A SOC analyst may encounter evidence that a protective control is:

- Missing
- Misconfigured
- Ineffective
- Bypassed
- Requiring improvement

For example:

```text
SOC Investigation
       ↓
Identifies Repeated Account Compromise
       ↓
Investigation Finds No MFA
       ↓
Protective Gap Identified
       ↓
Recommend MFA
       ↓
Reduce Future Risk
```

This demonstrates how SOC findings can contribute to broader cybersecurity risk management.

---

## 10. Connection Between IDENTIFY and PROTECT

The relationship between Day 2 and Day 3 can be understood as:

```text
IDENTIFY
    ↓
Understand Assets and Risks
    ↓
Determine What Needs Protection
    ↓
PROTECT
    ↓
Implement Appropriate Safeguards
```

For example:

```text
IDENTIFY
Employee VPN account has excessive privileges
        ↓
PROTECT
Apply least privilege + MFA
```

Another example:

```text
IDENTIFY
Critical server is running outdated software
        ↓
PROTECT
Patch and securely configure the platform
```

---

## 11. Key Learning

### PROTECT

Think:

What safeguards can we implement to manage cybersecurity risk?

```text
PROTECT
│
├── Identity & Access
│   ├── Authentication
│   ├── MFA
│   └── Least Privilege
│
├── Awareness & Training
│   ├── Phishing Awareness
│   ├── Security Training
│   └── Reporting
│
├── Data Security
│   ├── Encryption
│   ├── Access Control
│   └── Backup
│
├── Platform Security
│   ├── Patching
│   ├── Secure Configuration
│   └── Endpoint Security
│
└── Infrastructure Resilience
    ├── Redundancy
    ├── Failover
    └── Resilience
```

---

## 12. Interview Takeaways

### Q1. What is the PROTECT Function in NIST CSF 2.0?

The PROTECT Function focuses on implementing safeguards to manage cybersecurity risks in accordance with the organization's risk management strategy.

### Q2. What are the main Categories under PROTECT?

Identity Management, Authentication, and Access Control; Awareness and Training; Data Security; Platform Security; and Technology Infrastructure Resilience.

### Q3. How does MFA relate to NIST CSF?

MFA is a protective measure related to identity management, authentication, and access control. It helps reduce the risk associated with compromised credentials.

### Q4. Why is least privilege important?

Least privilege limits users and systems to the access they actually require, reducing the potential impact if an account or system is compromised.

### Q5. Is hashing the same as encryption?

No. Encryption is designed to protect data while allowing authorized parties to recover the original information. Hashing is generally used for purposes such as password verification and integrity checking.

### Q6. How does patching relate to PROTECT?

Keeping software updated and addressing vulnerabilities is part of protecting technology platforms and reducing the organization's attack surface.

---

## 13. What I Learned Today

- PROTECT focuses on implementing safeguards to manage cybersecurity risk.
- PROTECT contains five Categories:
  - Identity Management, Authentication, and Access Control
  - Awareness and Training
  - Data Security
  - Platform Security
  - Technology Infrastructure Resilience
- MFA strengthens authentication.
- Least privilege reduces unnecessary access.
- Security awareness helps reduce human-related security risks.
- Encryption can protect sensitive data at rest and in transit.
- Hashing and encryption serve different purposes.
- Patching and secure configuration help protect technology platforms.
- Infrastructure resilience helps organizations maintain or restore important operations during disruptions.
- Protective controls should be selected according to organizational risk and requirements.
- SOC findings can identify gaps in existing protective controls.

---

## Reference

### Primary Source

NIST Cybersecurity Framework (CSF) 2.0 — CSWP 29
National Institute of Standards and Technology (NIST)

<https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.29.pdf>
