# Lab 04 | Cybersecurity Incident Investigation

> [!IMPORTANT]
> **Objective:** Follow a structured Incident Response (IR) process through the phases of **Preparation → Identification → Containment → Eradication → Recovery → Lessons Learned**.

---

# 📖 Lab Overview

This lab introduces the Incident Response (IR) lifecycle using a simulated phishing and credential compromise scenario. You will investigate the incident, contain the threat, eradicate malicious activity, recover affected systems, and document the incident according to industry best practices.

The lab follows the standard incident response process recommended by leading cybersecurity frameworks.

---

# 🎯 Learning Objectives

Upon completing this lab, you will be able to:

- Investigate a suspected cybersecurity incident.
- Identify indicators of compromise (IOCs).
- Scope the impact of an attack.
- Contain compromised accounts and systems.
- Eradicate persistence mechanisms.
- Recover affected systems securely.
- Produce professional incident documentation.
- Capture lessons learned to improve future response activities.

---

# 📋 Scenario

## Scenario: Suspected Phishing & Credential Compromise

A user reports receiving a suspicious email. Shortly afterward, the Security Information and Event Management (SIEM) platform generates an alert indicating multiple failed login attempts followed by a successful login from an unusual IP address.

Your task is to investigate the incident using the Incident Response lifecycle.

---

# 🧪 Lab Tasks

## Step 1: Identification & Scoping

### Objective

Determine the scope and impact of the suspected security incident.

### Procedure

- Collect the suspicious email headers using **MXToolbox Email Header Analyzer**.
- Search the SIEM for the user's login events during the previous **24 hours**.
- Identify:
  - Source IP address of the successful login
  - Login timestamp
  - Affected user account
- Determine whether any files or sensitive data were accessed or exfiltrated by reviewing file access logs.

### Splunk Search – User Login Activity

```spl
# Splunk: find logins for a specific user

index=main EventCode=4624 Account_Name=jdoe
| table _time, src_ip, Logon_Type, Account_Name
```

> [!TIP]
> Establishing an accurate timeline early in the investigation helps determine the full scope of the incident.

---

## Step 2: Containment

### Objective

Prevent further unauthorized activity while preserving forensic evidence.

### Procedure

- Disable the compromised user account immediately in **Active Directory**.
- Block the attacker's source IP address at the firewall.
- Isolate the affected workstation from the network (if malware is suspected).
- Preserve volatile evidence by capturing a memory dump before isolation whenever possible.

### Disable an Active Directory Account

```powershell
# Disable AD account (PowerShell)

Disable-ADAccount -Identity jdoe

# Verify

Get-ADUser jdoe | Select Enabled
```

> [!WARNING]
> Preserve forensic evidence before performing containment actions that could modify or destroy critical investigation data.

---

## Step 3: Eradication

### Objective

Remove the threat and eliminate any persistence mechanisms.

### Procedure

- Reset the compromised user's password.
- Force re-authentication for the affected account.
- Check for persistence mechanisms, including:
  - Scheduled tasks
  - Startup entries
  - Newly created local administrator accounts
- Perform a full antivirus or Endpoint Detection and Response (EDR) scan of the affected workstation.
- Review every system that the compromised account had access to.

### Check Local Administrators

```cmd
# Check local admins on Windows

net localgroup administrators
```

### Check Scheduled Tasks

```cmd
# Check scheduled tasks

schtasks /query /fo LIST /v | findstr "Task Name"
```

> [!IMPORTANT]
> Removing persistence mechanisms is essential to prevent attackers from regaining access after remediation.

---

## Step 4: Recovery & Documentation

### Objective

Restore normal operations while documenting the incident for future reference.

### Procedure

- Re-enable the user account only after confirming the system is in a clean state.
- Enable Multi-Factor Authentication (MFA) before restoring user access.
- Document the complete incident timeline:

```text
Detection → Containment → Resolution
```

- Write a **Post-Incident Report (PIR)** covering:
  - Root cause
  - Incident timeline
  - Actions performed
  - Lessons learned
- Update the Incident Response (IR) playbook to address any gaps identified during the investigation.

> [!NOTE]
> Comprehensive documentation improves future incident response and supports audit and compliance requirements.

---

# ✅ Expected Outcome

By completing this lab, you will have:

- Investigated a phishing-related security incident.
- Identified indicators of compromise.
- Scoped the incident impact.
- Contained compromised accounts and systems.
- Removed persistence mechanisms.
- Restored secure operations.
- Produced a professional Post-Incident Report (PIR).
- Updated the Incident Response playbook with improvement recommendations.

---

# 💡 Best Practice Tips

> [!TIP]
>
> - Never skip the **Lessons Learned** phase—it is one of the most valuable parts of the Incident Response process.
> - Always preserve forensic evidence before performing containment activities that may destroy valuable data.
> - Use a dedicated incident tracking platform (for example, **TheHive** or **Jira**) instead of managing incidents through chat applications.
> - Provide status updates to stakeholders every **30–60 minutes** during active incidents.
> - Require **Multi-Factor Authentication (MFA)** before restoring access to compromised accounts, as passwords alone are insufficient.

---

# 📋 Deliverables

At the end of this lab, you should have the following documentation:

- ✅ Incident Timeline
- ✅ Login Investigation Results
- ✅ Email Header Analysis
- ✅ Indicators of Compromise (IOCs)
- ✅ Containment Actions Log
- ✅ Eradication Checklist
- ✅ Recovery Validation
- ✅ Post-Incident Report (PIR)
- ✅ Updated Incident Response Playbook

---

# 📌 Lab Summary

| Category | Details |
|-----------|---------|
| **Lab** | Lab 04 |
| **Title** | Cybersecurity Incident Investigation |
| **Primary Skill** | Incident Response (IR) |
| **Incident Type** | Phishing & Credential Compromise |
| **Framework** | Incident Response Lifecycle (Preparation → Identification → Containment → Eradication → Recovery → Lessons Learned) |
| **Difficulty** | Intermediate |
| **Estimated Duration** | 90–120 Minutes |
| **Deliverables** | Investigation Findings, Containment Log, Recovery Documentation, Post-Incident Report, Updated IR Playbook |

---
 
