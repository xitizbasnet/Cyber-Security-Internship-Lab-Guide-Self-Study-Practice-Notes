# Lab 08 | Log Review & Anomaly Detection

> [!IMPORTANT]
> **Objective:** Develop the skill of manually reviewing logs, build detection queries in a Security Information and Event Management (SIEM) platform, and identify patterns that indicate attacks or policy violations.

---

# 📖 Lab Overview

Logs are one of the most valuable sources of security intelligence. This lab focuses on analyzing Windows and Linux system logs, creating SIEM detection rules, and identifying suspicious activity that may indicate malicious behavior, security policy violations, or unauthorized access attempts.

You will learn how to investigate authentication events, identify Indicators of Compromise (IOCs), and automate detection through scheduled SIEM searches.

---

# 🎯 Learning Objectives

Upon completing this lab, you will be able to:

- Review Windows and Linux security logs.
- Identify common authentication events.
- Detect suspicious login behavior.
- Create SIEM detection queries.
- Analyze log data for anomalies.
- Schedule automated security detections.
- Recognize common Indicators of Compromise (IOCs).

---

# 📚 Key Windows Event IDs to Know

| Event ID | Description |
|----------|-------------|
| **4624** | Successful Logon |
| **4625** | Failed Logon |
| **4648** | Logon with Explicit Credentials (Pass-the-Hash indicator) |
| **4720** | User Account Created |
| **4732** | User Added to Security Group |
| **7045** | New Service Installed (Malware Persistence) |
| **4698** | Scheduled Task Created |

> [!TIP]
> Understanding common Windows Event IDs enables analysts to quickly identify suspicious authentication activity and privilege changes.

---

# 🧪 Lab Tasks

## Step 1: Review Raw Windows Security Logs

### Objective

Perform manual analysis of Windows Security Event Logs.

### Procedure

- Open:

```text
Event Viewer → Windows Logs → Security
```

- Filter logs by **Event ID 4625**.
- Count failed login attempts per user during the last hour.
- Identify accounts with **more than 10 failed login attempts**, which may indicate a brute-force attack.
- Export relevant events as a **CSV** file for additional analysis.

> [!NOTE]
> Multiple failed logins followed by a successful authentication often indicate credential guessing or password spraying activity.

---

## Step 2: Build SIEM Detection Queries

### Objective

Create detection rules for common attack techniques.

### Procedure

Create SIEM queries to detect:

- Brute-force login attempts.
- New administrator account creation.
- After-hours user logins (outside **8:00 AM – 7:00 PM**).

Save each query as a **Saved Search** and configure it to execute **hourly**.

### Brute Force Detection

```spl
# Brute force detection

index=main EventCode=4625
| bucket _time span=5m
| stats count by Account_Name, src_ip, _time
| where count > 10
```

### New Administrator Account Detection

```spl
# New admin account detection

index=main EventCode=4720 OR EventCode=4732
| table _time, Account_Name, Member_Name, src
```

> [!IMPORTANT]
> Scheduled searches provide continuous monitoring and reduce the likelihood of missed security events.

---

## Step 3: Analyse Linux Authentication Logs

### Objective

Review Linux authentication logs for unauthorized access attempts.

### Procedure

- Review authentication logs:
  - Ubuntu:

```text
/var/log/auth.log
```

- Red Hat Enterprise Linux (RHEL):

```text
/var/log/secure
```

- Use the **last** command to review recent login activity.
- Identify unusual login times.
- Review **/var/log/syslog** for:
  - Cron jobs
  - Newly started services

### SSH Failed Login Attempts

```bash
# SSH failed attempts

grep "Failed password" /var/log/auth.log \
| awk '{print $11}' \
| sort \
| uniq -c \
| sort -rn
```

### Recent Logins

```bash
# Recent logins

last -a | head -20
```

### Recently Started Services

```bash
# New services

grep "systemd" /var/log/syslog \
| grep "start" \
| tail -20
```

> [!TIP]
> Reviewing authentication logs alongside system logs helps establish timelines and identify abnormal system behavior.

---

# ✅ Expected Outcome

By completing this lab, you will have:

- Reviewed Windows Security Event Logs.
- Investigated failed and successful authentication attempts.
- Created SIEM detection rules.
- Scheduled automated security searches.
- Reviewed Linux authentication logs.
- Identified suspicious login behavior.
- Documented anomalous activity.

---

# 💡 Best Practice Tips

> [!TIP]
>
> - Centralize all security logs in a SIEM platform—locally stored logs can be modified, deleted, or lost.
> - Configure log retention for at least **12 months** for security logs to support compliance requirements such as **PCI DSS**.
> - Enable log integrity monitoring and generate alerts when logs are cleared or modified (for example, **Event ID 1102**).
> - Review privileged account activity **daily**, as administrator accounts are high-value targets for attackers.
> - Automate anomaly detection wherever possible; manual log review alone does not scale in enterprise environments.

---

# 📋 Deliverables

At the end of this lab, you should have the following documentation:

- ✅ Windows Security Log Review
- ✅ Exported Event Log (CSV)
- ✅ Brute Force Detection Query
- ✅ Administrator Account Detection Query
- ✅ After-Hours Login Detection Query
- ✅ Linux Authentication Log Analysis
- ✅ Suspicious Activity Report
- ✅ Detection Rule Documentation

---

# 📌 Lab Summary

| Category | Details |
|-----------|---------|
| **Lab** | Lab 08 |
| **Title** | Log Review & Anomaly Detection |
| **Primary Skill** | Security Monitoring & Log Analysis |
| **Focus Areas** | Windows Event Logs, Linux Authentication Logs, SIEM Detection Rules |
| **Platforms** | Windows, Linux, Splunk, Elastic |
| **Difficulty** | Intermediate |
| **Estimated Duration** | 60–90 Minutes |
| **Deliverables** | Log Analysis Report, SIEM Detection Queries, Suspicious Activity Report |

---
 
