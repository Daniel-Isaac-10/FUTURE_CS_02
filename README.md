# FUTURE_CS_02
# 🛡️ Cyber Security Internship – Task 2  
### Security Operations Center (SOC) Alert Monitoring & Incident Response  
**Organization:** Future Interns  
**Intern:** Daniel Isaac E  
**Domain:** Cyber Security  
**Date:** November 2025  

---

## 🔍 Overview  
This project was completed as part of my **Cyber Security Internship** under **Future Interns**.  
The task focuses on simulating real-world **Security Operations Center (SOC)** activities — analyzing log data, detecting suspicious activities, and preparing incident response documentation using SIEM tools.

The main objective was to gain practical experience in **log analysis, threat detection, and SIEM visualization** through **Elastic Stack (Kibana)** and **Splunk Cloud**.

---

## 🎯 Objectives  
- Understand how SOC teams monitor and respond to security alerts  
- Analyze simulated logs to identify abnormal patterns or threats  
- Use SIEM tools (Elastic Stack and Splunk) for visualization  
- Classify alerts by severity (High, Medium, Low)  
- Draft an Incident Response Report outlining threat mitigation strategies  

---

## 🧰 Tools & Technologies  
| Tool | Purpose |
|------|----------|
| **Elastic Stack (Kibana)** | Parsing, indexing, and analyzing logs |
| **Splunk Cloud** | SIEM dashboard creation and visualization |
| **SOC_Task2_Sample_Logs.txt** | Provided simulated SOC log dataset |
| **Microsoft Word** | Report documentation and analysis summary |

---

## ⚙️ Implementation Steps  

### **1. Elastic Stack Setup**  
- Uploaded the `SOC_Task2_Sample_Logs.txt` file into **Elastic Cloud**.  
- Created a custom **Ingest Pipeline** named `soc_task2_parse_pipeline` using Grok filters:  
%{TIMESTAMP_ISO8601:timestamp} | user=%{DATA:user} | ip=%{IP:source.ip} | action=%{DATA:event.action}( | threat=%{DATA:threat})?

markdown
Copy code
- Created an **Index**: `soc_task2_index`  
- Visualized parsed data using **Kibana Discover** to confirm structured fields like:
- `timestamp`
- `user`
- `source.ip`
- `event.action`
- `threat`

---

### **2. Splunk Configuration**  
- Imported the same log dataset into **Splunk Cloud**.  
- Created an index: `soc_task2_index`.  
- Ran the following SPL queries:
```spl
index=soc_task2_index | stats count by user
index=soc_task2_index | stats count by action
Built a Dashboard (SOC_Task2_Dashboard) with:

Bar Chart → Events by User

Pie Chart → Events by Action

3. Alert Analysis & Classification
High Severity: Multiple failed logins or malware detections

Medium Severity: Abnormal user activity or IP access

Low Severity: Standard login or routine system actions

These alerts were documented in the Incident Response Report with remediation and containment steps.

📊 Results
Successfully created a structured SIEM pipeline for log analysis.

Detected abnormal user patterns and security anomalies.

Designed and deployed dashboards for visual event analysis.

Simulated SOC reporting workflow from detection to resolution.

📄 Deliverables
📘 Incident Response Report: SOC_Task2_Report_Daniel_Isaac_E.docx

📁 Evidence Folder: Contains all screenshots from Elastic Stack & Splunk

🧾 Sample Logs: SOC_Task2_Sample_Logs.txt

🧠 Key Learnings
Hands-on exposure to SOC workflows and SIEM environments

Understanding log ingestion, parsing, and field mapping

Gained practical skills in threat detection and response simulation

Improved reporting and documentation techniques for professional cybersecurity work

🔗 References
Elastic Stack (ELK) Documentation

Splunk Official Documentation

Future Interns Official Website

📬 Acknowledgment
Special thanks to Future Interns for organizing this internship and guiding me through hands-on cybersecurity learning that closely resembles real SOC environments.

#futureinterns #cybersecurity #internship #SIEM #elasticstack #splunk #SOC #incidentresponse #loganalysis
