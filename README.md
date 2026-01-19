# splunk-windows-log-portfolio
Splunk portfolio using Windows system logs

Windows System Log Monitoring using Splunk

 Overview
This project demonstrates the ingestion, analysis, and visualization of my **Windows system logs** using **Splunk Enterprise**.  
The goal of this portfolio is to showcase hands-on experience with **log ingestion, SPL querying, dashboards, and alerts**

All data used in this project comes from **real Windows Event Logs** generated on my local machine.

---

 Objective
- Ingest Windows System,Application and Security logs into Splunk
- Monitor system health and application stability
- Detect security-related events such as failed login attempts/error
- Build dashboards and alerts for proactive monitoring
- Gain practical experience with Splunk Search Processing Language (SPL)

---

 Data Sources & Ingestion
Data Source: Windows Event Viewer  
- System Logs
- Application Logs
- Security Logs

Ingestion Method:
- Splunk Enterprise → Add Data → Local Event Logs

SPL Queries USed
1)index =main (Displays all the events)
2)index=main sourcetype="csv"
