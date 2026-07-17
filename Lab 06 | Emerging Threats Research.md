# Lab 06 | Emerging Threats Research

> [!IMPORTANT]
> **Objective:** Develop a structured approach to threat intelligence gathering, produce a Threat Intelligence Report, and map threats to the MITRE ATT&CK® framework.

---

# 📖 Lab Overview

Threat intelligence enables organizations to proactively identify, understand, and mitigate emerging cyber threats before they result in security incidents. In this lab, you will learn how to gather threat intelligence from trusted sources, analyze current threats, map attacker techniques to the MITRE ATT&CK® framework, and produce a professional Threat Intelligence Report.

---

# 🎯 Learning Objectives

Upon completing this lab, you will be able to:

- Identify reliable sources of cyber threat intelligence.
- Subscribe to and manage threat intelligence feeds.
- Research current cyber threats and security advisories.
- Identify Indicators of Compromise (IOCs) and adversary Tactics, Techniques, and Procedures (TTPs).
- Map attacks to the MITRE ATT&CK® framework.
- Assess organizational risk.
- Produce a professional Threat Intelligence Report.

---

# 🌐 Key Threat Intelligence Sources

| Source | Description |
|---------|-------------|
| **MITRE ATT&CK®** | attack.mitre.org — Adversary TTP framework |
| **CISA Advisories** | cisa.gov/known-exploited-vulnerabilities — Known Exploited Vulnerabilities (KEV) catalog |
| **NVD** | nvd.nist.gov — CVE database with CVSS scores |
| **Krebs on Security** | krebsonsecurity.com — Cybersecurity news and threat analysis |
| **ThreatFox** | threatfox.abuse.ch — Free IOC database |

> [!NOTE]
> Combining multiple threat intelligence sources provides better visibility and improves confidence in identified threats.

---

# 🧪 Lab Tasks

## Step 1: Subscribe to Threat Feeds

### Objective

Configure reliable threat intelligence sources to receive current cybersecurity advisories.

### Procedure

- Sign up for **CISA** free email alerts.
- Create an account on **OpenCTI** or **MISP** (free threat intelligence platforms).
- Import free threat feeds:
  - AbuseCH
  - AlienVault OTX
- Configure a weekly digest to review the **Top 5 threats every Monday morning**.

> [!TIP]
> Reviewing threat intelligence on a scheduled basis helps maintain awareness of emerging threats affecting your environment.

---

## Step 2: Research a Current Threat (e.g., Phishing Campaign)

### Objective

Analyze a recent cyber threat and map it to the MITRE ATT&CK® framework.

### Procedure

- Select a recent threat from:
  - CISA Known Exploited Vulnerabilities (KEV)
  - Threat news feeds
- Identify the following:
  - Threat Actor
  - Target Industry
  - Attack Vector
  - Indicators of Compromise (IOCs)
    - IP Addresses
    - Domains
    - File Hashes
- Map the attack to the appropriate **MITRE ATT&CK®** tactics and techniques.
- Identify which organizational security controls would detect or prevent the attack.

### MITRE ATT&CK® Example Mapping

```text
Tactic:
Initial Access

Technique:
T1566.001 - Spearphishing Attachment

Sub-technique:
Malicious macro in Office document

Mitigation:
M1049 - Antivirus/Antimalware
M1017 - User Training
```

> [!IMPORTANT]
> Mapping attacks to MITRE ATT&CK® provides a standardized method for understanding adversary behavior and improving defensive capabilities.

---

## Step 3: Produce a Threat Intelligence Report

### Objective

Create a structured report summarizing the analyzed threat and recommended defensive actions.

### Report Structure

#### Executive Summary

Provide a brief overview (2–3 sentences) describing:

- What happened
- Who is at risk

#### Technical Details

Include:

- Indicators of Compromise (IOCs)
- Tactics, Techniques, and Procedures (TTPs)
- Affected software
- Affected software versions

#### Impact Assessment

Evaluate:

- Likelihood of exploitation
- Potential impact on your organization

#### Recommendations

Document recommended mitigation actions, such as:

- Apply security patches
- Block malicious IP addresses and domains
- Block file hashes where applicable
- Conduct user awareness training
- Monitor for related Indicators of Compromise (IOCs)

#### Review

- Share the report with your supervisor.
- Incorporate feedback before final publication.

> [!NOTE]
> Threat intelligence reports should be concise, actionable, and tailored to the organization's operational environment.

---

# ✅ Expected Outcome

By completing this lab, you will have:

- Configured multiple threat intelligence sources.
- Researched a current cybersecurity threat.
- Identified Indicators of Compromise (IOCs).
- Mapped attacker techniques to the MITRE ATT&CK® framework.
- Evaluated organizational risk.
- Produced a professional Threat Intelligence Report.

---

# 💡 Best Practice Tips

> [!TIP]
>
> - Verify Indicators of Compromise (IOCs) against multiple trusted sources before taking action—false IOCs can waste valuable incident response resources.
> - Prioritize threats that are relevant to your industry (for example, financial services), as not every advisory applies equally to every organization.
> - Maintain a threat register to track mitigated threats and those that remain open.
> - Share sanitized threat intelligence with trusted industry peers whenever appropriate, as collaboration strengthens the broader security community.
> - Always attribute threat intelligence to its original source to ensure credibility, transparency, and traceability.

---

# 📋 Deliverables

At the end of this lab, you should have the following documentation:

- ✅ Threat Intelligence Feed Configuration
- ✅ Current Threat Analysis
- ✅ Indicators of Compromise (IOC) List
- ✅ MITRE ATT&CK® Mapping
- ✅ Risk Assessment
- ✅ Threat Intelligence Report
- ✅ Recommended Mitigation Plan

---

# 📌 Lab Summary

| Category | Details |
|-----------|---------|
| **Lab** | Lab 06 |
| **Title** | Emerging Threats Research |
| **Primary Skill** | Cyber Threat Intelligence |
| **Focus Areas** | Threat Research, IOC Analysis, MITRE ATT&CK®, Risk Assessment |
| **Threat Intelligence Sources** | MITRE ATT&CK®, CISA KEV, NVD, Krebs on Security, ThreatFox |
| **Difficulty** | Intermediate |
| **Estimated Duration** | 60–90 Minutes |
| **Deliverables** | Threat Intelligence Report, IOC List, MITRE ATT&CK® Mapping, Risk Assessment |

---
 
