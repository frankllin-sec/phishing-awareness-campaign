# 🛡️ Phishing Awareness Campaign — Security Awareness Project

> **Author:** Frankllin | [github.com/frankllin-sec](https://github.com/frankllin-sec)  
> **Role:** SOC Analyst Student | Blue Team  
> **Date:** April 2026  


---

## 📌 Project Overview

This project simulates a real-world **Security Awareness Campaign** focused on phishing attack prevention, created as part of my SOC Analyst training. As a SOC Analyst, one of the key responsibilities is not only detecting threats but also **educating employees** to recognize and avoid social engineering attacks before they become incidents.

This campaign was created as if I were a SOC Analyst sending an official internal security awareness communication to all company employees.

---

## 🎯 Objective

> **"The best firewall is an educated employee."**

The goal of this project was to:

- Create a professional phishing awareness banner for internal distribution
- Educate non-technical employees on how to recognize phishing emails
- Provide clear and actionable steps for employees to follow
- Demonstrate real SOC Analyst skills beyond just technical detection

---

## 🧠 Why This Matters

Phishing is the **#1 initial attack vector** in cybersecurity. Understanding this from a SOC perspective means:

| Statistic | Data |
|---|---|
| % of breaches starting with phishing | **91%** |
| Phishing emails sent daily worldwide | **3.4 Billion** |
| Average cost of a phishing breach | **$4.9 Million** |
| Time to detect a phishing breach | **197 days average** |

A SOC Analyst who understands phishing from both a **technical detection** perspective AND a **user education** perspective is significantly more valuable to any organization.

---

## 📋 What Was Created

### Security Awareness Banner
A professional corporate-style security awareness poster designed to be distributed to all company employees via:
- Internal email blast
- Company intranet / internal portal
- Slack / Microsoft Teams channel
- Printed and posted in office common areas

### Banner Content Covers:
- ✅ How to identify a phishing email
- ✅ 8 red flags employees must recognize
- ✅ Real phishing email example with annotations
- ✅ What to do if you clicked a suspicious link
- ✅ How to report suspicious emails to the SOC team
- ✅ Key statistics to create urgency and awareness

---

## 🔍 Red Flags Covered in the Banner

### ❌ What to AVOID:

**1. Suspicious Sender Address**
Always verify the full email address — not just the display name. Attackers use spoofed domains like `support@paypa1.com` or `hr@company-secure.net`

**2. Urgent or Threatening Language**
Phrases like *"Your account will be suspended in 24 hours"* are classic manipulation tactics designed to bypass rational thinking.

**3. Unexpected Attachments**
Never open `.exe`, `.zip`, `.docm` files from unknown senders. Even PDF files can contain malicious macros.

**4. Suspicious or Misspelled Links**
Hover over links before clicking. Watch for: `arnazon.com`, `paypa1.com`, `micros0ft.com` or unusually long URLs.

### ✅ What to DO:

**5. Verify the Sender Directly**
If you receive an unexpected request claiming to be from IT or your CEO — call them directly before taking action.

**6. Check Links Before Clicking**
Hover your mouse over any link to preview the real destination URL at the bottom of your browser.

**7. Report Suspicious Emails**
Forward suspicious emails to the IT Security team immediately. Do not delete them — they are evidence.

**8. Never Enter Credentials on Unknown Sites**
Legitimate companies will NEVER ask for your password via email.

---

## 📧 Real Phishing Email Example

The banner includes an annotated example of a real phishing email showing:

```
FROM:    IT Support <it-support@c0mpany-help.net>  ⚠️ FAKE DOMAIN
SUBJECT: ⚠️ URGENT: Your password expires today    ⚠️ URGENCY TACTIC

BODY: Dear Employee,
Your corporate account will be deactivated in 24 hours.
Click here to verify your credentials immediately...

LINK: http://company-secure-login.suspicious-domain.net/verify
      ⚠️ NOT a company domain — PHISHING LINK
```

**Annotations highlight:**
- Fake sender domain with number substitution (`c0mpany` vs `company`)
- Urgency language creating panic
- Suspicious link with fake domain
- Generic greeting instead of employee name

---

## 🆘 Incident Response — If You Clicked

The banner provides clear 4-step guidance for employees who accidentally clicked:

```
STEP 1 → Disconnect from network immediately
STEP 2 → Do NOT enter any credentials on the page
STEP 3 → Contact IT Security team immediately
STEP 4 → Change your passwords from a safe device
```

---

## 🔗 Connection to SOC Work

This campaign directly connects to the technical SOC work of detecting phishing:

### Splunk Detection Query — Phishing Indicators
```spl
index=email sourcetype=mail_logs
| search subject="*urgent*" OR subject="*password*" OR subject="*verify*"
| stats count by sender_domain, subject, recipient
| where count > 5
| sort -count
```

### What a SOC Analyst Looks for in Email Logs:
- High volume of emails with urgent subject lines
- Emails from external domains impersonating internal addresses
- Emails containing links to newly registered domains
- Attachments with suspicious file extensions
- EventCode **4625** spikes after bulk phishing campaigns

---

## 🛠️ Tools and Skills Demonstrated

| Skill | Application |
|---|---|
| **Security Awareness** | Created professional employee-facing content |
| **Phishing Analysis** | Deep understanding of phishing tactics and indicators |
| **SOC Communication** | Translating technical threats into user-friendly language |
| **Incident Response** | Clear employee guidance for post-click scenarios |
| **Splunk SPL** | Detection queries for email-based threats |
| **Threat Intelligence** | Real statistics and attack patterns |

---

## 📁 Project Structure

```
phishing-awareness-campaign/
│
├── README.md                          ← This file
├── awareness-banner/
│   └── phishing-awareness-banner.png  ← The awareness banner image
├── splunk-queries/
│   └── phishing-detection.spl         ← SPL queries for detection
└── docs/
    └── phishing-indicators-ioc.md     ← IOC reference document
```

---

## 📚 What I Learned

Working on this project reinforced several key SOC Analyst concepts:

1. **Phishing is the most common attack vector** — understanding it deeply from both attacker and defender perspective is essential
2. **Employee education reduces SOC workload** — when users report suspicious emails, analysts can investigate proactively
3. **Clear communication is a SOC skill** — translating technical threats into actionable guidance for non-technical users
4. **Awareness campaigns complement technical controls** — no firewall can stop a user who willingly enters credentials on a fake site

---

This project is part of my ongoing cybersecurity training:

## 🔗 Related Projects

| Project | Description | Link |
|---|---|---|
| SOC Phishing Investigation | Hands-on phishing alert investigation using TryHackMe SOC Simulator | [View Project](https://github.com/frankllin-sec/Soc-phishing-investigation) |
| Threat IP Investigation | Suspicious IP analysis using OSINT tools | [View Project](https://github.com/frankllin-sec/Project-2---ip-investigation-) |
| Cybersecurity Journey | Full documentation of my SOC Analyst learning path | [View Journey](https://github.com/frankllin-sec/Mycybersecurity-journey) |

---

## ⚠️ Disclaimer

This project was created purely for **educational and portfolio purposes** as part of SOC Analyst training. The phishing email example shown is a simulation created to demonstrate attack patterns. No real phishing attacks were conducted.

---

<p align="center">
  <img src="https://img.shields.io/badge/Type-Security%20Awareness-dc2626?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Focus-Phishing%20Prevention-f97316?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Role-SOC%20Analyst-2563eb?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Status-Completed-16a34a?style=for-the-badge"/>
</p>

<p align="center">
  Made with 🛡️ by <a href="https://github.com/frankllin-sec">Frankllin</a>
</p>
