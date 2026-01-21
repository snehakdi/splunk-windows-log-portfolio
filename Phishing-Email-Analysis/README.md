# Phishing Email Analysis Project 
## Project Overview

This project demonstrates a **phishing email analysis workflow** . The objective is to identify, analyze, and document indicators of phishing using a real-world style email sample that impersonates a trusted organization (Apple) and attempts to lure users into clicking a malicious link.

The analysis focuses on:

* Identifying social engineering tactics
* Detecting email header and content anomalies
* Analyzing suspicious URLs
* Documenting Indicators of Compromise (IOCs)
* Providing a clear security conclusion


---

## Objective

* Determine whether the email is legitimate or malicious
* Identify red flags commonly used in phishing attacks
* Extract and document relevant IOCs
* Demonstrate analytical thinking and reporting

---

## Analysis Approach

* **Email Client (Outlook/Gmail view)** – To inspect sender details and message formatting
* **Manual Header & Content Analysis** – Reviewing sender address, subject line, and email body
* **URL Hover Analysis** – Comparing visible link text with actual destination URL
* **Threat Analysis Mindset (No link interaction)** – Links were not clicked 


---

## Email Summary

* **Subject:** Important alert for MAC users about HP printers
* **Sender Display Name:** Apple
* **Sender Email Address:**  printing@apple-account-support.com
* **Target Audience:** macOS users
* **Call to Action:** Urgent update required via provided link

---

## Observations & Analysis

### 1. Suspicious Subject Line

* Uses urgent language: **"Important alert"**
* Designed to create fear and prompt immediate action

### 2. Sender Email Address Anomaly

* Domain used: `apple-account-support.com`
* Legitimate Apple emails typically come from `@apple.com`
* Indicates **domain impersonation**

### 3. Inconsistent Branding and Formatting

* "MAC" written in all caps instead of the standard **"Mac"**
* Generic greeting: **"Dear Apple User"** instead of a personalized name

### 4. Urgent Call-to-Action (Social Engineering)

* Claims HP printer certificates were revoked
* Pressures the user to click a link immediately to restore functionality

### 5. Suspicious URL

* Displayed link text:

   https://www.PrinterConnect.org/hp-certificate

* Hovered / actual URL contains unrelated and suspicious keywords such as:

  * `password-changes`
  * `phishwall`
* URL does not belong to Apple or HP

### 6. Lack of Legitimate Contact Information

* Signature only states **"Apple Team"**
* No official support links, phone numbers, or ticket references

---

Please refer these screenshots[ 1.png](https://github.com/snehakdi/SOC-Projects/blob/main/Phishing-Email-Analysis/Screenshots/Phishing1.png),[2.png](https://github.com/snehakdi/SOC-Projects/blob/main/Phishing-Email-Analysis/Screenshots/Phishing2.png)

## Indicators of Compromise (IOCs)

| Type               | Indicator                         |
| ------------------ | --------------------------------- |
| Email Domain       | apple-account-support.com         |
| Suspicious URL     | PrinterConnect.org/hp-certificate |
| Social Engineering | Urgent update request             |
| Impersonation      | Apple branding misuse             |

---

## Risk Assessment

* **Threat Type:** Phishing 
* **Impact:** High – Potential compromise of Apple credentials
* **Likelihood:** High – Common impersonation technique

---

## Conclusion

This email is a **clear phishing attempt** designed to impersonate Apple and exploit user trust through urgency and fear-based messaging. Multiple red flags were identified, including a spoofed sender domain, suspicious URLs, lack of legitimate contact information, and social engineering tactics.

A SOC Level 1 analyst should:

* Immediately flag and report the email
* Block the sender domain and URL
* Educate users on phishing indicators
* Escalate to SOC L2 if multiple users are targeted

## Disclaimer

This project is for **educational and portfolio purposes only**. No malicious links were accessed during the analysis,Only a screenshot of the email was taken that was used for educational purpose.
