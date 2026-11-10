# Day 9: Insider Threat Profile Analysis

**Case**: Lone Star Energy Ops Insider Threat Investigation  
**Date**: 2026-11-10  
**Investigator**: Sorin Rodriguez  
**Document ID**: docs/07_insider_threat_profile.md  

---

## ?? Subject Overview & Background

| Field | Details |
| :--- | :--- |
| **Suspect Identifier** | Subject Alpha / j.doe |
| **Assigned Role** | Junior Systems Administrator |
| **Access Authorization Level** | Tier 2 Internal Network & Workstation Management |
| **Department** | Enterprise IT & Operations |
| **Employment Status** | Active (Pending HR / Security Hold) |

---

## ?? Threat Profile Breakdown

### 1. Primary Motive & Opportunity
* **Motive**: Financial gain paired with workplace grievance following a passed-over promotion.
* **Opportunity**: Over-privileged network permissions and off-hours VPN remote access without mandatory Multi-Factor Authentication (MFA) enforcement.

### 2. Attack Vectors & Exploited Vulnerabilities
* **Credential Abuse**: Used legitimate domain credentials outside standard operating hours to bypass basic border filters.
* **Privilege Escalation**: Exploited local administrative rights on Workstation-04 using custom PowerShell scripts to elevate to SYSTEM access.
* **SCADA Network Probing**: Leveraged escalated rights to cross network segments into restricted operational technology (OT) log directories.

### 3. Exfiltration & Evasion Tactics
* **Data Staging**: Aggregated and compressed target telemetry data into encrypted archives (.tar.gz) to bypass automated Data Loss Prevention (DLP) scanners.
* **Data Exfiltration**: Outbound SSH tunneling to an external untrusted IP address (45.33.32.156).
* **Defense Evasion**: Executed Event Log clearing utilities (wevtutil cl System) to obliterate evidence of local execution.

---

## ?? Forensic Findings & Risk Rating
* **Insider Risk Level**: **HIGH** (Intentional Data Theft & Evasion Execution)
* **Impact Assessment**: Unauthorized exposure of critical infrastructure logs and potential operational technology disruption.
