# Lab 09 | IT & Security Team Collaboration

> [!IMPORTANT]
> **Objective:** Understand how security teams collaborate with IT operations, use ticketing systems for security tasks, and contribute to joint IT-security projects.

---

# 📖 Lab Overview

Effective cybersecurity requires strong collaboration between security teams, IT operations, system administrators, and business stakeholders. This lab focuses on operational workflows that enable security teams to work effectively with IT teams through ticketing systems, change management processes, and security reviews.

You will practice managing security-related requests, participating in change approval processes, and reviewing network security controls collaboratively.

---

# 🎯 Learning Objectives

Upon completing this lab, you will be able to:

- Understand IT and security collaboration workflows.
- Use ticketing systems to manage security tasks.
- Create and manage security-related requests.
- Participate in Change Advisory Board (CAB) processes.
- Review firewall rules using security best practices.
- Communicate security risks effectively with technical and non-technical teams.

---

# 🛠️ Suggested Tools

| Tool | Purpose |
|------|---------|
| **GLPI** | Open-source IT service management and ticketing platform |
| **Jira Cloud** | Cloud-based issue and workflow management platform |
| **Ticketing System** | Security task tracking and audit documentation |
| **Firewall Management Console** | Firewall rule review and cleanup |

---

# 🧪 Lab Tasks

## Step 1: Set Up a Security Ticketing Workflow

### Objective

Create a structured workflow for managing security-related tasks and requests.

### Procedure

- Install **GLPI** or use a free **Jira Cloud** project for ticket management.
- Create the following ticket categories:

| Category | Purpose |
|----------|---------|
| **Vulnerability** | Security weaknesses requiring remediation |
| **Incident** | Active or suspected security incidents |
| **Change Request** | Planned security or infrastructure changes |
| **Access Request** | User access or permission changes |

- Define Service Level Agreements (SLAs):

| Priority | Response Time |
|----------|---------------|
| **Critical** | 4 hours |
| **High** | 8 hours |
| **Medium** | 24 hours |
| **Low** | 72 hours |

- Create a sample ticket for a vulnerability identified during **Lab 02**.

> [!TIP]
> A ticketing system provides accountability, visibility, and an audit trail for security activities.

---

## Step 2: Participate in a Change Advisory Board (CAB) Simulation

### Objective

Practice the change management process for implementing security fixes.

### Scenario

Create a change request for patching a critical server based on vulnerability findings from **Lab 02**.

### Procedure

Draft a Change Request containing:

- Change Description
- Risk Assessment
- Rollback Plan
- Maintenance Window

Example structure:

| Field | Description |
|-------|-------------|
| Change Description | Details of the planned security change |
| Risk Assessment | Potential impact and associated risks |
| Rollback Plan | Steps to restore the previous state if required |
| Maintenance Window | Approved implementation timeframe |

Additional steps:

- Present the change request to your supervisor for approval simulation.
- Document the approved change.
- Implement the approved change within your lab environment.

> [!NOTE]
> Change management ensures security improvements are implemented in a controlled and auditable manner.

---

## Step 3: Joint Firewall Rule Review Exercise

### Objective

Collaboratively review firewall rules to ensure security and operational requirements are met.

### Procedure

- Request the current firewall rule list from your IT team or simulate a firewall rule inventory.
- Review each firewall rule for:

  - Purpose
  - Expiration date
  - Ownership
  - Least privilege compliance

- Identify orphaned firewall rules:

  - No documented owner
  - No documented business purpose
  - No expiration date

- Submit a firewall cleanup request through the ticketing system.

> [!IMPORTANT]
> Firewall rules should only exist when there is a documented business requirement and responsible owner.

---

# ✅ Expected Outcome

By completing this lab, you will have:

- Created a security ticketing workflow.
- Managed security-related tickets.
- Practiced change management procedures.
- Participated in a CAB approval simulation.
- Reviewed firewall rules.
- Identified and documented unnecessary access rules.
- Improved collaboration between IT operations and security teams.

---

# 💡 Best Practice Tips

> [!TIP]
>
> - Security should act as a **business enabler**, not only a blocker—collaborate with teams to achieve secure outcomes.
> - Communicate security issues using business language with non-technical stakeholders by focusing on risk and impact rather than only technical details such as CVEs.
> - Every firewall rule should have:
>   - A documented owner
>   - A business purpose
>   - An expiration or review date
> - Use ticketing systems for all changes because verbal approvals are not auditable.
> - Build strong relationships with IT operations teams, as successful incident response depends on effective collaboration.

---

# 📋 Deliverables

At the end of this lab, you should have the following documentation:

- ✅ Security Ticket Workflow
- ✅ Sample Vulnerability Ticket
- ✅ Change Request Document
- ✅ CAB Approval Record
- ✅ Firewall Rule Review Report
- ✅ Firewall Cleanup Request
- ✅ Collaboration Workflow Documentation

---

# 📌 Lab Summary

| Category | Details |
|-----------|---------|
| **Lab** | Lab 09 |
| **Title** | IT & Security Team Collaboration |
| **Primary Skill** | Security Operations Collaboration |
| **Focus Areas** | Ticket Management, Change Management, Firewall Governance |
| **Tools** | GLPI, Jira Cloud, Ticketing Systems |
| **Difficulty** | Beginner–Intermediate |
| **Estimated Duration** | 60–90 Minutes |
| **Deliverables** | Security Tickets, Change Request, Firewall Review Report |

---
 
