# Lab 10 | Security Awareness Training Activities

> [!IMPORTANT]
> **Objective:** Design a phishing simulation, create security awareness training content, and measure the effectiveness of a security awareness program.

---

# 📖 Lab Overview

Security awareness is a critical component of an organization's cybersecurity strategy. Employees are often targeted through phishing, social engineering, and other human-focused attack techniques.

This lab focuses on creating and evaluating security awareness activities, including phishing simulations, employee education materials, and effectiveness measurement.

---

# 🎯 Learning Objectives

Upon completing this lab, you will be able to:

- Design and conduct a controlled phishing simulation.
- Analyze employee security awareness metrics.
- Identify areas requiring additional security education.
- Create security awareness training materials.
- Measure training effectiveness through assessments.
- Promote a positive security culture.

---

# 🧪 Lab Tasks

## Step 1: Design a Phishing Simulation

### Objective

Create a safe phishing simulation to evaluate employee awareness and identify improvement opportunities.

### Procedure

- Use **GoPhish** (free, open-source) to create a simulated phishing campaign.
- Install GoPhish on a local virtual machine.
- Download GoPhish from:

```text
getgophish.com
```

- Create a phishing email template that simulates an IT password reset request.
- Configure a landing page to capture:
  - Email open activity
  - Link click activity

> [!WARNING]
> Do **not** collect real user credentials during phishing simulations. The purpose is security awareness testing, not credential collection.

- Run the campaign against:
  - Lab virtual machines, or
  - Volunteer colleagues

### Start GoPhish

```bash
# Start GoPhish

./gophish
```

### Access Administration Panel

```text
https://localhost:3333
```

### Default Credentials

```text
Username: admin
Password: gophish
```

> [!TIP]
> Always obtain appropriate authorization before conducting phishing simulations and clearly define the scope of testing.

---

## Step 2: Analyse Campaign Results

### Objective

Evaluate phishing simulation performance and identify opportunities for improvement.

### Procedure

Review the following metrics:

| Metric | Description |
|--------|-------------|
| **Open Rate** | Percentage of users who opened the phishing email |
| **Click Rate** | Percentage of users who clicked the simulated phishing link |
| **Credential Submission Rate** | Percentage of users who entered information on the landing page |

Additional analysis:

- Identify departments or roles with the highest click rates.
- Identify users who repeatedly interact with phishing simulations.
- Assign mandatory remedial security awareness training where required.
- Document findings in a report for management review.

> [!NOTE]
> Simulation results should be used to improve security awareness, not to punish employees.

---

## Step 3: Create Awareness Training Content

### Objective

Develop educational material to improve employee cybersecurity awareness.

### Procedure

Create a **5-slide presentation** covering:

1. **Phishing**
   - Identifying suspicious emails
   - Recognizing phishing indicators

2. **Password Hygiene**
   - Strong passwords
   - Password reuse risks
   - Multi-Factor Authentication (MFA)

3. **Social Engineering**
   - Manipulation techniques
   - Common attacker tactics

4. **Safe Browsing**
   - Recognizing unsafe websites
   - Avoiding malicious downloads

5. **Incident Reporting**
   - How to report suspicious activity
   - Importance of timely reporting

Additional requirements:

- Include anonymized examples from the phishing simulation.
- Create a **5-question quiz** to test knowledge retention.
- Deliver training through:
  - Email communication, or
  - Short lunch-and-learn session

> [!TIP]
> Short, practical, and scenario-based training is generally more effective than lengthy security awareness sessions.

---

# ✅ Expected Outcome

By completing this lab, you will have:

- Created a phishing simulation campaign.
- Measured employee response behavior.
- Analyzed security awareness metrics.
- Developed employee training materials.
- Created a knowledge assessment quiz.
- Produced an awareness improvement report.

---

# 💡 Best Practice Tips

> [!TIP]
>
> - Conduct phishing simulations quarterly because threat landscapes and employee behavior change over time.
> - Never publicly shame employees who fail phishing tests—use results for positive education and improvement.
> - Keep security awareness training short (**5–10 minutes**) because long sessions reduce information retention.
> - Measure improvement over time by tracking click rates across multiple simulation rounds.
> - Celebrate improvements because positive reinforcement builds stronger security culture more effectively than fear-based approaches.

---

# 📋 Deliverables

At the end of this lab, you should have the following documentation:

- ✅ Phishing Simulation Plan
- ✅ GoPhish Campaign Configuration
- ✅ Campaign Results Report
- ✅ User Awareness Analysis
- ✅ Security Awareness Presentation
- ✅ Knowledge Assessment Quiz
- ✅ Management Summary Report

---

# 📌 Lab Summary

| Category | Details |
|-----------|---------|
| **Lab** | Lab 10 |
| **Title** | Security Awareness Training Activities |
| **Primary Skill** | Security Awareness & Human Risk Management |
| **Focus Areas** | Phishing Simulation, Employee Training, Awareness Metrics |
| **Tool** | GoPhish |
| **Difficulty** | Beginner–Intermediate |
| **Estimated Duration** | 60–90 Minutes |
| **Deliverables** | Phishing Campaign Report, Training Content, Awareness Assessment |

---
 
