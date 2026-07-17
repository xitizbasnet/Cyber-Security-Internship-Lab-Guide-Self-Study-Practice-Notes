# Lab 01 | Security Monitoring & Alert Analysis

> [!IMPORTANT]
> **Objective:** Learn to monitor security alerts in real time using Security Information and Event Management (SIEM) platforms, understand alert classification, and perform initial alert triage.

---

## 📖 Lab Overview

This lab introduces the fundamentals of security monitoring and alert analysis using a SIEM platform. You will learn how to:

- Monitor SIEM dashboards.
- Triage security alerts.
- Classify security incidents.
- Configure basic alert rules.
- Document and escalate security events.

---

## 🎯 Learning Objectives

Upon completing this lab, you will be able to:

- Monitor security alerts in real time using SIEM platforms.
- Understand the security alert lifecycle.
- Configure basic SIEM alert rules.
- Perform initial alert triage.
- Classify alerts based on investigation findings.
- Document and escalate security incidents appropriately.

---

# 🛠️ Tools Required

| Tool | Purpose |
|------|---------|
| **Splunk Free / Elastic SIEM** | SIEM platform for log ingestion and alerting |
| **Windows Event Viewer** | Native Windows log source |
| **Syslog / rsyslog** | Linux log forwarding |
| **Wazuh (Optional)** | Open-source SIEM & EDR |

---

# 🧪 Lab Tasks

## Step 1: Set Up a SIEM Environment

### Objective

Install and configure a SIEM platform to ingest and monitor log data.

### Procedure

- Download and install **Splunk Free Edition** on your lab VM (Windows/Linux).
- Start Splunk.
- Open a web browser and navigate to:

```text
http://localhost:8000
```

- Complete the initial setup.
- Navigate to:

```text
Settings > Data Inputs
```

- Add a **Monitor** input for a log directory.
- Verify that log data is flowing into Splunk by searching:

```spl
index=main | head 20
```

### Verify Log Ingestion

```spl
# Splunk search to verify ingestion

index=main sourcetype=* | stats count by sourcetype
```

> [!TIP]
> Ensure data is successfully indexed before proceeding to alert creation.

---

## Step 2: Configure Basic Alert Rules

### Objective

Create a basic alert that triggers when a predefined event threshold is exceeded.

### Procedure

- Go to **Alerts** in Splunk.
- Select **Create Alert**.
- Configure the following trigger condition:

```text
Number of events > 5 in 5 minutes
```

- Choose the following alert action:

```text
Log to Triggered Alerts
```

- Save the alert.
- Simulate events to trigger the alert.
- Review triggered alerts by navigating to:

```text
Activity > Triggered Alerts
```

> [!NOTE]
> Triggered alerts should appear in the **Triggered Alerts** panel after sufficient events are generated.

---

## Step 3: Triage an Alert

### Objective

Perform an initial investigation of a triggered alert.

### Procedure

- Open a triggered alert.
- Review the raw log entries.
- Identify the following information:
  - Source IP
  - Destination IP
  - Timestamp
  - Event Type
- Classify the alert as one of the following:
  - True Positive
  - False Positive
  - Benign
- Document your findings in a triage ticket (use a simple spreadsheet).
- Escalate **True Positives** for further investigation (Lab 04).

### Sample Splunk Search

```spl
# Sample Splunk search for failed logins

index=main EventCode=4625
| stats count by Account_Name, src_ip
| where count > 5
```

> [!IMPORTANT]
> Accurate documentation during triage is essential for incident tracking and future investigations.

---

# ✅ Expected Outcome

By completing this lab, you will have:

- A functioning SIEM environment.
- An understanding of the security alert lifecycle.
- Experience configuring basic alert rules.
- The ability to triage and classify security alerts.
- Experience documenting investigation findings.

---

# 💡 Best Practice Tips

> [!TIP]
>
> - Always document every alert you triage—even false positives help tune detection rules.
> - Tune alert thresholds regularly to reduce alert fatigue; prioritize **High** and **Critical** severity alerts.
> - Correlate multiple low-severity alerts before dismissing them, as attackers often chain together seemingly minor events.
> - Use **UTC timestamps** consistently across all SIEM sources to avoid correlation errors.
> - Never disable an alert rule without manager approval and documented justification.

---

# 📌 Lab Summary

| Category | Details |
|-----------|---------|
| **Lab** | Lab 01 |
| **Title** | Security Monitoring & Alert Analysis |
| **Primary Skill** | SIEM Monitoring & Alert Triage |
| **Difficulty** | Beginner |
| **Estimated Duration** | 60–90 Minutes |
| **Deliverables** | Configured SIEM, Triggered Alert, Triage Documentation |

---
