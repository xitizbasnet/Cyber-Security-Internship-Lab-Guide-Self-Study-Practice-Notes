# Lab 07 | Endpoint, Network & Application Security

> [!IMPORTANT]
> **Objective:** Apply security hardening to an endpoint, configure network security controls, and perform basic web application security testing.

---

# 📖 Lab Overview

This lab introduces three essential areas of defensive cybersecurity:

- **Endpoint Security** – Harden Windows systems using security best practices.
- **Network Security** – Configure host and network-based security controls to reduce attack surfaces.
- **Application Security** – Perform basic web application security testing against a deliberately vulnerable application in a controlled lab environment.

The exercises are designed to reinforce secure configuration practices while introducing common defensive controls used in enterprise environments.

---

# 🎯 Learning Objectives

Upon completing this lab, you will be able to:

- Harden Windows endpoints using recommended security configurations.
- Configure host-based firewall rules and network segmentation.
- Implement intrusion detection rules.
- Validate network controls using security testing tools.
- Perform basic web application security testing.
- Identify common OWASP Top 10 vulnerabilities.
- Document security findings and remediation recommendations.

---

# 🧪 Lab Tasks

## Step 1: Endpoint Hardening (Windows)

### Objective

Apply baseline security hardening to a Windows endpoint.

### Procedure

- Disable unused services:
  - Telnet
  - FTP
  - Print Spooler (if not required)
- Enable **Windows Defender Firewall** on all profiles:
  - Domain
  - Private
  - Public
- Configure **AppLocker** to allow only approved applications.
- Enable **BitLocker** on the system drive to protect data at rest.
- Configure detailed audit logging through Group Policy for:
  - Logon
  - Object Access
  - Process Creation

### Disable Telnet Service

```powershell
# Disable Telnet service

Set-Service -Name TlntSvr -StartupType Disabled
Stop-Service TlntSvr
```

### Enable Process Creation Auditing

```powershell
# Enable audit process creation

auditpol /set /subcategory:"Process Creation" /success:enable /failure:enable
```

> [!TIP]
> Endpoint hardening reduces the available attack surface and improves visibility into system activity.

---

## Step 2: Network Security Controls

### Objective

Implement foundational network security controls to protect systems from unauthorized access.

### Procedure

- Configure a host-based firewall rule to block inbound traffic on **TCP Port 23 (Telnet)**.
- Implement network segmentation by placing:
  - Servers in a dedicated VLAN.
  - Workstations in a separate VLAN.
- Configure an Intrusion Detection System (IDS) rule using **Snort** or **Suricata** to detect port scanning activity.
- Test firewall rules using **Nmap** from an external host.

### Example Snort Rule – Detect Port Scan

```snort
alert tcp any any -> $HOME_NET any (
    msg:"Port Scan Detected";
    flags:S;
    threshold:type both, track by_src, count 20, seconds 5;
    sid:10001;
    rev:1;
)
```

> [!NOTE]
> Network segmentation limits lateral movement and helps contain security incidents.

---

## Step 3: Web Application Security Testing (OWASP Top 10)

### Objective

Perform basic security testing against a deliberately vulnerable web application in a safe lab environment.

### Procedure

- Deploy **DVWA (Damn Vulnerable Web Application)** on a local virtual machine.
- Test for **SQL Injection**:
  - Enter the following payload in the login field:

```text
' OR 1=1--
```

- Test for **Cross-Site Scripting (XSS)**:
  - Enter the following payload into an input field:

```javascript
alert('XSS')
```

- Test for default credentials:
  - `admin / admin`
  - `admin / password`
- Document each finding, including:
  - Vulnerability type
  - Payload used
  - Risk level
  - Recommended fix

### Install DVWA with Docker

```bash
# Install DVWA with Docker

docker run -d -p 8080:80 vulnerables/web-dvwa
```

### Access the Application

```text
http://localhost:8080
```

### Default Credentials

```text
Username: admin
Password: password
```

> [!WARNING]
> Perform web application security testing **only** against systems that you own or have explicit written authorization to test. DVWA is intentionally vulnerable and should only be deployed in an isolated laboratory environment.

---

# ✅ Expected Outcome

By completing this lab, you will have:

- Hardened a Windows endpoint.
- Configured host-based firewall protections.
- Implemented network segmentation concepts.
- Created and tested IDS detection rules.
- Performed basic web application security testing.
- Identified common OWASP Top 10 vulnerabilities.
- Documented findings and remediation recommendations.

---

# 💡 Best Practice Tips

> [!TIP]
>
> - Only test applications for which you have **explicit written permission**—always.
> - Use **CIS Benchmarks** as the baseline for endpoint hardening because they provide comprehensive, industry-recognized security guidance.
> - Segment networks so that workstations, servers, and IoT devices reside on separate VLANs whenever possible.
> - Deploy a **Web Application Firewall (WAF)** to provide additional protection for production web applications; secure coding practices alone are not sufficient.
> - Regularly update web frameworks, libraries, and dependencies, as many OWASP Top 10 vulnerabilities exploit unpatched software.

---

# 📋 Deliverables

At the end of this lab, you should have the following documentation:

- ✅ Endpoint Hardening Checklist
- ✅ Windows Security Configuration
- ✅ Firewall Configuration
- ✅ Network Segmentation Design
- ✅ IDS Rule Configuration
- ✅ Nmap Validation Results
- ✅ Web Application Security Assessment
- ✅ OWASP Findings Report
- ✅ Remediation Recommendations

---

# 📌 Lab Summary

| Category | Details |
|-----------|---------|
| **Lab** | Lab 07 |
| **Title** | Endpoint, Network & Application Security |
| **Primary Skill** | Defensive Security Implementation |
| **Focus Areas** | Endpoint Hardening, Network Security, Application Security |
| **Security Standards** | CIS Benchmarks, OWASP Top 10 |
| **Difficulty** | Intermediate |
| **Estimated Duration** | 90–120 Minutes |
| **Deliverables** | Hardened Endpoint, Firewall Rules, IDS Configuration, Web Application Security Assessment |

---
 
