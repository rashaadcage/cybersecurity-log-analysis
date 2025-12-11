# 🔐 Cybersecurity Log Analysis & Threat Detection  
**Author:** Rashaad Cage  
**Role:** Cybersecurity Analyst  

---

## 📌 Overview  
This project simulates a real-world security investigation using system authentication logs.  
The goal is to detect suspicious activity such as:

- Brute-force login attempts  
- Failed → successful login sequences  
- After-hours access  
- Privilege escalation events  
- Unusual or high-risk IP activity  

This project demonstrates core cybersecurity skills including log analysis, threat detection, incident investigation, SQL/KQL-style querying, and incident reporting.

---

## 📁 Dataset Description  
The dataset (`cyber_logs.csv`) includes simulated SIEM-style log data with fields such as:

- Timestamp  
- Username  
- Source IP  
- Event Type (login success, login failure, escalation)  
- Status  
- Device  

These logs allow identification of patterns that indicate security threats.

---

## 🛠 Tools Used  
- **Excel / CSV Review** — initial log inspection  
- **Python / Pandas** — log parsing and threat detection logic  
- **Security Analysis Logic** — building hypotheses and identifying risk  
- **Visualization** — summary chart included as `cyber_event_chart.png`  

---

## 🔎 Key Threat Indicators  
The investigation focuses on detecting:

- Multiple failed login attempts from the same IP (brute force)  
- Failed logins followed by a successful login (credential compromise)  
- Privilege escalation events  
- Logins outside normal business hours  
- Logins from unfamiliar device names  
- Suspicious login patterns tied to specific user accounts  

---

## 📊 Visuals  
This repository includes:

- `cyber_event_chart.png` — a visual summary of flagged suspicious events

Optional visuals you could add:

- Failed login heatmap  
- Login time distribution chart  
- High-risk IP summary  

---

## 🧠 SQL / KQL-Style Queries  

### 1️⃣ Detect brute-force login patterns  
```sql
SELECT source_ip, COUNT(*) AS failed_attempts
FROM cyber_logs
WHERE status = 'failed'
GROUP BY source_ip
HAVING COUNT(*) > 5;
