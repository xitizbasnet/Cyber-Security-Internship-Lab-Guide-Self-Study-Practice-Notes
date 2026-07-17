# Lab 05 | Security Policy & Documentation Management

> [!IMPORTANT]
> **Objective:** Understand the hierarchy of security documents, draft a security policy, and implement a document management workflow.

---

# 📖 Lab Overview

This lab introduces the principles of security governance through policy development and documentation management. You will learn how to create security policies, define security standards, manage document versions, and establish a structured review process that aligns with industry best practices.

---

# 🎯 Learning Objectives

Upon completing this lab, you will be able to:

- Understand the hierarchy of information security documentation.
- Draft a professional **Acceptable Use Policy (AUP)**.
- Develop a password standard aligned with organizational security requirements.
- Configure password policies in Windows or Linux environments.
- Implement document version control and review workflows.
- Apply security governance best practices.

---

# 📚 Document Hierarchy

The following hierarchy illustrates how security documentation is organized within an Information Security Management System (ISMS).

| Document Type | Description |
|--------------|-------------|
| **Policy** | High-level management intent (e.g., Acceptable Use Policy) |
| **Standard** | Specific mandatory requirements (e.g., Password Standard) |
| **Procedure** | Step-by-step instructions to implement a standard |
| **Guideline** | Recommended but optional best practices |

> [!NOTE]
> Policies define **what** must be achieved, standards define **mandatory requirements**, procedures explain **how** to perform a task, and guidelines provide **recommended practices**.

---

# 🧪 Lab Tasks

## Step 1: Draft an Acceptable Use Policy (AUP)

### Objective

Create a formal Acceptable Use Policy that defines appropriate use of organizational information systems.

### Procedure

Structure your Acceptable Use Policy (AUP) using the following sections:

- Purpose
- Scope
- Policy Statements
- Violations
- Review Date

Include policy statements covering:

- Internet use
- Email use
- Device usage
- Data handling
- Remote access

Reference the following ISO 27001 controls:

- **A.8** — Asset Management
- **A.6.2** — Mobile Devices

After completing the draft:

- Request a peer review.
- Verify clarity, completeness, and consistency.

> [!TIP]
> Security policies should be concise, easy to understand, and enforceable across the organization.

---

## Step 2: Create a Password Standard

### Objective

Develop and implement a password standard that supports secure authentication practices.

### Password Requirements

- Minimum **12 characters**
- Combination of:
  - Uppercase letters
  - Lowercase letters
  - Numbers
  - Special characters
- Prevent reuse of the last **10 passwords**
- Maximum password age of **90 days**
- Multi-Factor Authentication (MFA) required for:
  - All privileged accounts
  - All remote access accounts

Implement and validate the policy using:

- **Group Policy (Windows)**, or
- **PAM (Linux)**

### Apply Password Policy via Group Policy (PowerShell)

```powershell
# Apply password policy via GPO (PowerShell)

Set-ADDefaultDomainPasswordPolicy `
-MinPasswordLength 12 `
-PasswordHistoryCount 10 `
-MaxPasswordAge 90.00:00:00 `
-ComplexityEnabled $true
```

> [!IMPORTANT]
> Password policies should balance strong security requirements with organizational usability.

---

## Step 3: Implement Document Version Control

### Objective

Create a controlled document management process for security documentation.

### Procedure

- Create a **SharePoint** library or **Git** repository for policy documents.
- Configure metadata fields for each document:
  - Version
  - Status (Draft / Approved / Retired)
  - Owner
  - Next Review Date
- Configure automated review reminders:
  - **30 days** before the annual review date.
- Archive superseded document versions using a consistent naming convention.

Example:

```text
AUP_v1.2_archived
```

> [!NOTE]
> Effective version control ensures document integrity, traceability, and compliance with governance requirements.

---

# ✅ Expected Outcome

By completing this lab, you will have:

- Created an Acceptable Use Policy (AUP).
- Developed a Password Standard.
- Configured password policy settings.
- Implemented document version control.
- Established a policy review workflow.
- Applied information security governance best practices.

---

# 💡 Best Practice Tips

> [!TIP]
>
> - Review all security policies at least **annually**—outdated policies can create significant security risks.
> - Write policies in plain language so employees can understand them without specialized legal or technical knowledge.
> - Assign a named owner to every policy who is responsible for maintaining and updating the document.
> - Communicate policy updates to all staff via email and require signed acknowledgment where appropriate.
> - Periodically test documented procedures (for example, through tabletop exercises) to confirm they remain effective before an actual incident occurs.

---

# 📋 Deliverables

At the end of this lab, you should have the following documentation:

- ✅ Acceptable Use Policy (AUP)
- ✅ Password Standard
- ✅ Password Policy Configuration
- ✅ Document Version Control Repository
- ✅ Policy Metadata Structure
- ✅ Policy Review Schedule
- ✅ Archived Policy Versions

---

# 📌 Lab Summary

| Category | Details |
|-----------|---------|
| **Lab** | Lab 05 |
| **Title** | Security Policy & Documentation Management |
| **Primary Skill** | Information Security Governance |
| **Focus Areas** | Policy Development, Security Standards, Documentation Management |
| **Related Controls** | ISO 27001 A.8, ISO 27001 A.6.2 |
| **Difficulty** | Beginner–Intermediate |
| **Estimated Duration** | 60–90 Minutes |
| **Deliverables** | Acceptable Use Policy, Password Standard, Version-Controlled Documentation Repository |

---

 
