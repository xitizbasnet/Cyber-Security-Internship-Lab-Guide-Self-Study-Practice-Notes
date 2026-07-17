# Lab 11 | Security Tools Hands-On

> [!IMPORTANT]
> **Objective:** Gain practical hands-on experience with industry-standard security tools referenced in cybersecurity roles, including **Wireshark**, **Nmap**, **Burp Suite**, and **Nessus**.

---

# 📖 Lab Overview

Security professionals rely on specialized tools to analyze networks, identify vulnerabilities, test applications, and investigate security events.

This lab provides practical experience with commonly used cybersecurity tools:

- **Wireshark** — Network packet capture and analysis.
- **Nmap** — Network discovery and service scanning.
- **Burp Suite** — Web application security testing.
- **Nessus** — Vulnerability assessment and scanning.

> [!WARNING]
> Perform security testing only on systems and networks that you own or have explicit written authorization to assess.

---

# 🎯 Learning Objectives

Upon completing this lab, you will be able to:

- Capture and analyze network packets using Wireshark.
- Perform network discovery and vulnerability scanning with Nmap.
- Intercept and analyze web requests using Burp Suite.
- Identify common web application security weaknesses.
- Generate security assessment evidence and reports.
- Apply security tools responsibly within authorized environments.

---

# 🧰 Required Tools

| Tool | Purpose |
|------|---------|
| **Wireshark** | Network packet capture and protocol analysis |
| **Nmap** | Port scanning, service discovery, and vulnerability detection |
| **Burp Suite Community Edition** | Web application security testing |
| **Nessus** | Vulnerability assessment and reporting |

---

# Part A: Wireshark — Network Packet Analysis

## Step 1: Capture and Analyse Traffic

### Objective

Capture network traffic and analyze protocols, connections, and communication patterns.

### Procedure

- Launch **Wireshark**.
- Start capturing traffic on your active network interface.
- Open a browser and navigate to an **HTTP website** (not HTTPS) to observe cleartext traffic.
- Apply the following display filters:

### HTTP Traffic Filter

```text
http
```

Observe:

- HTTP GET requests
- HTTP POST requests

### Identify New TCP Connections

```text
tcp.flags.syn==1 && tcp.flags.ack==0
```

### Follow a TCP Stream

- Right-click a captured packet.
- Select:

```text
Follow > TCP Stream
```

### Useful Wireshark Filters

```text
# HTTP traffic
http

# DNS queries
dns

# Traffic to/from a specific IP
ip.addr == 192.168.1.10

# HTTPS traffic
tcp.port == 443

# Ping packets
icmp
```

> [!NOTE]
> Packet captures provide valuable forensic evidence and can help identify suspicious network activity.

---

# Part B: Nmap — Port & Service Scanning

## Step 2: Advanced Nmap Scans

### Objective

Perform network reconnaissance and identify exposed services.

### Procedure

- Run a stealth SYN scan against your lab target.
- Perform operating system fingerprinting.
- Detect service versions.
- Run NSE scripts to identify potential vulnerabilities.
- Export scan results for documentation.

---

## SYN Stealth Scan

```bash
# SYN Stealth Scan

nmap -sS 192.168.1.10
```

---

## OS Detection and Service Version Detection

```bash
# OS Detection + Service Version

nmap -O -sV 192.168.1.10
```

---

## Vulnerability Detection Using NSE Scripts

```bash
# Vulnerability scripts

nmap --script vuln 192.168.1.10
```

---

## Export Results to XML

```bash
# Export to XML

nmap -oX scan_results.xml 192.168.1.10
```

> [!TIP]
> Exporting scan results allows security teams to maintain evidence and track remediation activities.

---

# Part C: Burp Suite — Web Application Testing

## Step 3: Intercept and Analyse Web Requests

### Objective

Analyze web application traffic and identify common security weaknesses.

### Procedure

- Launch **Burp Suite Community Edition**.
- Configure the browser proxy:

```text
127.0.0.1:8080
```

- Navigate to **DVWA** from Lab 07.
- Allow Burp Suite to intercept web requests.
- Use **Burp Repeater** to modify and resend requests.
- Test for:

  - SQL Injection
  - Cross-Site Scripting (XSS)
  - Insecure Direct Object References (IDOR)
  - Insecure cookies

- Review HTTP response headers, including:

```text
X-Frame-Options
Content-Security-Policy (CSP)
Strict-Transport-Security (HSTS)
```

> [!IMPORTANT]
> Burp Suite testing should only be performed against authorized applications and controlled environments.

---

# ✅ Expected Outcome

By completing this lab, you will have:

- Captured and analyzed network traffic using Wireshark.
- Performed network reconnaissance using Nmap.
- Identified services and potential vulnerabilities.
- Intercepted and modified web requests using Burp Suite.
- Performed basic web security testing.
- Generated security evidence for reporting.

---

# 💡 Best Practice Tips

> [!TIP]
>
> - Only use **Wireshark** on networks you own or have explicit permission to monitor.
> - Save Wireshark captures as `.pcap` files for evidence collection; they may support forensic investigations.
> - Never run Nmap scans against internet-facing systems without written authorization, as unauthorized scanning may violate laws or policies.
> - Burp Suite can intercept HTTPS traffic; understand certificate handling and certificate pinning before testing mobile applications.
> - Practice these tools regularly in a controlled home lab environment—tool proficiency improves through consistent hands-on experience.

---

# 📋 Deliverables

At the end of this lab, you should have the following documentation:

- ✅ Wireshark Packet Capture (`.pcap`)
- ✅ Traffic Analysis Notes
- ✅ Nmap Scan Results
- ✅ XML Scan Report
- ✅ Burp Suite Testing Notes
- ✅ Web Application Security Findings
- ✅ Security Assessment Summary

---

# 📌 Lab Summary

| Category | Details |
|-----------|---------|
| **Lab** | Lab 11 |
| **Title** | Security Tools Hands-On |
| **Primary Skill** | Security Tool Proficiency |
| **Tools Covered** | Wireshark, Nmap, Burp Suite, Nessus |
| **Focus Areas** | Network Analysis, Scanning, Web Testing, Vulnerability Assessment |
| **Difficulty** | Intermediate |
| **Estimated Duration** | 90–120 Minutes |
| **Deliverables** | Packet Analysis Report, Scan Results, Web Security Assessment |

---

 
