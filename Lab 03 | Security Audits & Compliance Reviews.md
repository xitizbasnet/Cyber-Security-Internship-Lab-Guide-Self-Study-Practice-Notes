# Lab 03 | Security Audits & Compliance Reviews

> [!IMPORTANT]
> **Objective:** Understand how to plan and execute a structured security audit, map security controls to recognized compliance frameworks (ISO 27001 and NIST Cybersecurity Framework), and produce a professional security audit report.

---

# 📖 Lab Overview

This lab introduces the fundamentals of security auditing and compliance reviews. You will learn how to assess system security against established benchmarks, collect audit evidence, evaluate compliance, and prepare an audit report with actionable recommendations.

---

# 🎯 Learning Objectives

Upon completing this lab, you will be able to:

- Define the scope of a security audit.
- Build an audit checklist using recognized security benchmarks.
- Collect technical evidence to validate security controls.
- Map findings to compliance frameworks such as **ISO 27001** and **NIST CSF**.
- Assign risk ratings based on likelihood and impact.
- Produce a structured security audit report.
- Develop a remediation roadmap for identified security gaps.

---

# 🛠️ Suggested Tools & References

| Tool / Resource | Purpose |
|-----------------|---------|
| **CIS Benchmarks** | Security configuration standards for operating systems and applications |
| **CIS-CAT Lite** | Automated CIS Benchmark compliance assessment |
| **Windows Local Security Policy** | Review Windows security settings |
| **Linux Terminal** | Review Linux security configuration and patch status |
| **Spreadsheet (Excel / LibreOffice / Google Sheets)** | Audit checklist and findings documentation |
| **ISO 27001 Annex A** | Security control mapping |
| **NIST Cybersecurity Framework (CSF)** | Compliance and security maturity reference |

---

# 🧪 Lab Tasks

## Step 1: Define Audit Scope & Checklist

### Objective

Establish the audit scope and prepare a structured checklist for evaluating security controls.

### Procedure

- Select a target system (for example, a Windows Server in your lab).
- Download the **CIS Benchmark** for the selected operating system from **cisecurity.org**.
- Create a spreadsheet checklist containing the following columns:
  - Control ID
  - Description
  - Status
  - Evidence
  - Risk
- Classify each control into one of the following categories:
  - Technical
  - Administrative
  - Physical

> [!TIP]
> A clearly defined audit scope helps ensure consistent coverage and avoids unnecessary assessment activities.

---

## Step 2: Conduct the Audit

### Objective

Evaluate the target system against the selected security benchmark and collect supporting evidence.

### Procedure

- Run the **CIS-CAT Lite** scanner against the target system.
- Review each failed security control.
- Capture supporting evidence, such as:
  - Screenshots
  - Command output
  - Configuration settings
- Review password policy:
  - **Windows:** Local Security Policy
  - **Linux:** `/etc/pam.d`
- Verify the operating system patch level.

### Linux Patch Status Check

```bash
# Linux patch status check

uname -r
apt list --upgradable 2>/dev/null | grep -v WARNING
```

### Windows Patch Information

```powershell
# Windows patch info

systeminfo | findstr "Hotfix"
```

> [!NOTE]
> Audit evidence should clearly demonstrate how each control was validated.

---

## Step 3: Map Findings to Compliance Controls

### Objective

Associate identified security gaps with recognized compliance controls and assign risk ratings.

### Procedure

- Map each finding to its corresponding **ISO 27001 Annex A** control.
  - Example:
    - **A.12.6.1** — Patch Management
- Assign a risk rating:
  - High
  - Medium
  - Low
- Identify compensating controls when direct remediation is not immediately possible.
- Record management acceptance for risks that will remain open.

> [!IMPORTANT]
> Risk acceptance should always be documented and formally approved by management.

---

## Step 4: Write the Audit Report

### Objective

Prepare a professional audit report summarizing findings and recommendations.

### Include the Following Sections

#### Executive Summary

Provide a one-paragraph overview describing:

- Audit scope
- Audit objectives
- Key findings

#### Findings Table

Document each finding using the following format:

| Control | Gap Description | Risk Rating | Recommendation |
|----------|-----------------|-------------|----------------|
| Example | Weak password policy | High | Enforce password complexity requirements |

#### Remediation Roadmap

Create a prioritized remediation plan including:

- Responsible owner
- Target completion date
- Priority
- Current status

#### Conclusion

Summarize the organization's overall compliance posture.

Example:

```text
Overall Compliance Rating: 68% Compliant
```

---

# ✅ Expected Outcome

By completing this lab, you will have:

- Defined the scope of a security audit.
- Conducted a structured compliance assessment.
- Collected and documented audit evidence.
- Mapped findings to ISO 27001 controls.
- Assigned risk ratings.
- Produced a professional security audit report.
- Created a remediation roadmap.

---

# 💡 Best Practice Tips

> [!TIP]
>
> - Keep all audit evidence archived—findings without supporting evidence are only opinions.
> - Always conduct audits with a **read-only** mindset: observe and record; never modify production systems during an audit.
> - Use a standardized risk scoring matrix to ensure consistent risk ratings across multiple audits.
> - Schedule follow-up audits within **90 days** after remediation to verify corrective actions.
> - Maintain the confidentiality of audit findings and share reports only on a need-to-know basis.

---

# 📋 Deliverables

At the end of this lab, you should have the following documentation:

- ✅ Audit Scope Document
- ✅ Security Audit Checklist
- ✅ CIS-CAT Assessment Results
- ✅ Audit Evidence (Screenshots and Command Output)
- ✅ Compliance Mapping Table
- ✅ Risk Assessment
- ✅ Security Audit Report
- ✅ Remediation Roadmap

---

# 📌 Lab Summary

| Category | Details |
|-----------|---------|
| **Lab** | Lab 03 |
| **Title** | Security Audits & Compliance Reviews |
| **Primary Skill** | Security Auditing & Compliance Assessment |
| **Frameworks** | ISO 27001, NIST CSF, CIS Benchmarks |
| **Difficulty** | Intermediate |
| **Estimated Duration** | 90–120 Minutes |
| **Deliverables** | Audit Checklist, Evidence Collection, Compliance Mapping, Audit Report, Remediation Roadmap |

---
 
