# Lab 12 | Frameworks & Standards

> [!IMPORTANT]
> **Objective:** Understand the structure and purpose of three major cybersecurity frameworks, map real-world security controls to each framework, and produce a framework comparison matrix.

---

# 📖 Lab Overview

Cybersecurity frameworks provide structured guidance for managing security risks, implementing controls, and improving organizational security maturity.

This lab focuses on three widely adopted frameworks:

- **ISO 27001** — Information Security Management System (ISMS) standard.
- **NIST Cybersecurity Framework (CSF)** — Security risk management framework.
- **OWASP** — Web application security guidance and testing standards.

You will learn how to map security activities to frameworks, identify gaps, assess maturity, and create improvement recommendations.

---

# 🎯 Learning Objectives

Upon completing this lab, you will be able to:

- Understand the purpose and structure of major security frameworks.
- Map security controls to ISO 27001 requirements.
- Apply the NIST CSF functions to incident scenarios.
- Evaluate web application security using OWASP guidance.
- Identify security gaps and recommend improvements.
- Create a framework comparison matrix.

---

# 📚 Framework Overview

| Framework | Key Focus |
|-----------|-----------|
| **ISO 27001** | International standard for Information Security Management Systems (ISMS); Annex A contains 93 controls (2022 edition) |
| **NIST CSF** | US cybersecurity framework based on five functions: Identify, Protect, Detect, Respond, Recover |
| **OWASP** | Web application security framework covering Top 10 risks, ASVS, and Testing Guide |

---

# 🧪 Lab Tasks

# Step 1: Map Controls — ISO 27001 Annex A

## Objective

Understand ISO 27001 security controls and map them to practical security implementations.

## Procedure

- Download the **ISO 27001:2022 control list** using publicly available summaries.
- Select five controls from different categories, such as:

  - **A.5 — Organizational Controls**
  - **A.8 — Technological Controls**

For each selected control, document:

- Control requirement.
- How the control is implemented in your lab environment.
- Identified gaps.
- Recommended remediation actions.

---

## Example ISO 27001 Control Mapping

| Category | Details |
|----------|---------|
| **Control** | ISO 27001 A.8.8 — Management of Technical Vulnerabilities |
| **Requirement** | Timely identification and remediation of technical vulnerabilities |
| **Implementation** | Weekly Nessus scans with a 30-day remediation SLA |
| **Gap** | No automated patch deployment |
| **Remediation** | Implement WSUS/SCCM for automated patching |

---

> [!TIP]
> Control mapping helps organizations understand how technical activities support governance and compliance objectives.

---

# Step 2: Apply NIST CSF to a Scenario

## Objective

Apply the NIST Cybersecurity Framework to a real-world incident scenario.

## Scenario

Use the phishing incident from **Lab 04** as the assessment scenario.

---

## Procedure

Map each Incident Response activity to the appropriate NIST CSF function:

| NIST CSF Function | Example Activity |
|-------------------|------------------|
| **Identify** | Identify affected assets, users, and risks |
| **Protect** | Apply security controls such as MFA and user awareness training |
| **Detect** | Identify suspicious activity through SIEM alerts |
| **Respond** | Contain and investigate the incident |
| **Recover** | Restore services and apply lessons learned |

---

## Security Maturity Assessment

Assess your organization's maturity for each NIST CSF function using a scale of **1–4**:

| Score | Maturity Level |
|-------|----------------|
| **1** | Initial |
| **2** | Developing |
| **3** | Defined |
| **4** | Optimized |

---

## Create a NIST CSF Roadmap

Document improvements planned for the next six months.

Example:

| Area | Improvement |
|------|-------------|
| Detect | Improve SIEM alert coverage |
| Protect | Expand MFA adoption |
| Respond | Update incident response procedures |

---

# Step 3: OWASP Top 10 Mapping Exercise

## Objective

Evaluate application security risks using OWASP standards.

## Procedure

Complete the following activities:

- For each OWASP Top 10 category (**A01–A10**):
  - Identify one real-world CVE example.
- Test your DVWA instance for at least three OWASP Top 10 vulnerabilities.
- Document remediation actions for each finding:

  - Code changes
  - Configuration updates
  - Web Application Firewall (WAF) rules

- Review the **OWASP ASVS Level 1 checklist**.
- Assess DVWA against the checklist.

---

## OWASP Finding Documentation Format

| Field | Description |
|-------|-------------|
| Vulnerability | Identified OWASP category |
| CVE Example | Related vulnerability reference |
| Testing Method | How the issue was identified |
| Risk Level | Severity assessment |
| Remediation | Fix recommendation |

---

> [!NOTE]
> OWASP resources provide practical guidance for securing applications throughout the software development lifecycle.

---

# 📊 Framework Comparison Matrix

| Area | ISO 27001 | NIST CSF | OWASP |
|------|-----------|----------|-------|
| Primary Purpose | ISMS governance and compliance | Cybersecurity risk management | Application security improvement |
| Main Audience | Security leaders, auditors, organizations | Security teams and executives | Developers, testers, application security teams |
| Focus Area | Organizational security controls | Security lifecycle management | Web application security |
| Example Usage | Certification and compliance | Security maturity assessment | Secure development and testing |

---

# ✅ Expected Outcome

By completing this lab, you will have:

- Mapped security controls to ISO 27001.
- Applied NIST CSF to an incident scenario.
- Evaluated application security using OWASP.
- Identified security gaps.
- Created remediation recommendations.
- Produced a cybersecurity framework comparison matrix.

---

# 💡 Best Practice Tips

> [!TIP]
>
> - Frameworks are guides, not simple checklists—adapt them according to your organization's risk appetite and business requirements.
> - Start with **NIST CSF** for security maturity assessments because it is widely understood and freely available.
> - Use **OWASP** resources regularly because they provide practical application security guidance.
> - Cross-reference frameworks: an ISO 27001 compliance gap often aligns with a NIST CSF maturity gap.
> - Achieving ISO 27001 certification requires strong management commitment, governance, and continuous improvement—not only technical controls.

---

# 📋 Deliverables

At the end of this lab, you should have the following documentation:

- ✅ ISO 27001 Control Mapping Document
- ✅ Security Gap Assessment
- ✅ Remediation Recommendations
- ✅ NIST CSF Maturity Assessment
- ✅ Six-Month Security Improvement Roadmap
- ✅ OWASP Top 10 Mapping Report
- ✅ DVWA Security Assessment
- ✅ Framework Comparison Matrix

---

# 📌 Lab Summary

| Category | Details |
|-----------|---------|
| **Lab** | Lab 12 |
| **Title** | Frameworks & Standards |
| **Primary Skill** | Security Governance & Compliance |
| **Frameworks Covered** | ISO 27001, NIST CSF, OWASP |
| **Focus Areas** | Control Mapping, Risk Assessment, Security Maturity, Application Security |
| **Difficulty** | Intermediate |
| **Estimated Duration** | 90–120 Minutes |
| **Deliverables** | Framework Mapping, Maturity Assessment, OWASP Review, Improvement Roadmap |

---
 
