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
Data Source:[ Windows Event Viewer ](https://github.com/snehakdi/splunk-windows-log-portfolio/blob/main/screenshots/event%20viewer.png) 
- System Logs
- Application Logs
- Security Logs

Ingestion Method:
- Splunk Enterprise → Add Data → Local Event Logs

---

SPL Queries Used

1)index =main (Displays all the events) 
2)[index=main sourcetype="csv"](https://github.com/snehakdi/splunk-windows-log-portfolio/blob/main/screenshots/sourcetype.png) (displays all events whose sourcetype is csv) 

3)Filtering Queries

  ->[index=main sourcetype=csv Id=10016](https://github.com/snehakdi/splunk-windows-log-portfolio/blob/main/screenshots/Filtering.png) (displays all events whose id's are 10016) 
  ->[index=main sourcetype=csv UserId="S-1-5-18"](https://github.com/snehakdi/splunk-windows-log-portfolio/blob/main/screenshots/Filtering%20III.png) (displays all events whose USerid's are S-1-5-18) 
  ->[index=main sourcetype=csv Message=" "](https://github.com/snehakdi/splunk-windows-log-portfolio/blob/main/screenshots/Filtering%20IV.png) (displays all events whose Message is " ") 
   ->Visual representation of errors,warnings,information using [Pie chart](https://github.com/snehakdi/splunk-windows-log-portfolio/blob/main/screenshots/Visual%20representation.png)


  LOGON BEHAVIOUR ANALYSIS USING SECURITY LOGS
 [ index=main EventID=4624 | stats count by LogonType](https://github.com/snehakdi/splunk-windows-log-portfolio/blob/main/screenshots/Security.png)

 LogonType 2 (Interactive): Local user logins via keyboard and screen.

LogonType 7 (Unlock): Users unlocking existing sessions

LogonType 5 (Service): Windows services authenticating

LogonType 11 (Cached Interactive): Offline logins using cached credentials

No LogonType 3 (Network) or LogonType 10 (RDP) events were observed.

🔐 Security Interpretation

The observed logon types indicate normal user and system behavior.
The absence of network and RDP logons suggests:

No lateral movement activity

No remote access attempts

No unauthorized external logins during the analysis period

[index=main EventID=4624 LogonType=7
| table _time](https://github.com/snehakdi/splunk-windows-log-portfolio/blob/main/screenshots/logontype.png)
Monitored Windows Security Event ID 4624 (LogonType 7) to track workstation unlock events. This helps establish normal user behavior and confirms the absence of remote or unauthorized access activity.
 
  
