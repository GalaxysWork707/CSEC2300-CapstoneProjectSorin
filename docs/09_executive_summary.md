# Day 11: Executive Summary & Stakeholder User Stories

**Case**: Lone Star Energy Ops Insider Threat Investigation  
**Date**: 2026-11-17  
**Investigator**: Sorin Rodriguez  
**Document ID**: docs/09_executive_summary.md  

---

## ?? Executive Overview

On November 2, 2026, unauthorized off-hours access and data exfiltration occurred within the Lone Star Energy Ops enterprise network. Digital forensic analysis confirmed that internal employee j.doe (Junior Systems Administrator) leveraged valid credentials and over-privileged workstation permissions to access restricted SCADA telemetry logs, stage compressed archives, and exfiltrate data to an external IP (45.33.32.156) via SSH before attempting to clear local Windows Event Logs.

### Business & Operational Impact
* **Confidentiality Impact**: **High** — Sensitive SCADA operational telemetry was staged and transmitted outside the corporate perimeter.
* **Integrity Impact**: **Medium** — Local system audit logs on Workstation-04 were purged (wevtutil cl System), requiring reliance on centralized firewall and VPN logs.
* **Availability Impact**: **Low** — No disruption to active energy grid operations or SCADA control loops occurred.
* **Regulatory Exposure**: Potential notification requirements under federal critical infrastructure guidelines and state data breach statutes.

---

## ?? Agile Stakeholder User Stories (Executive & Legal)

* **Executive Leadership (CEO / Board)**:  
  *"As an Executive Stakeholder, I want a clear, non-technical summary of the breach scope, operational impact, and regulatory exposure so that I can make informed business decisions and authorize remediation budgets."*
* **General Counsel / Legal Team**:  
  *"As Legal Counsel, I want assurance that all digital evidence was collected under a strict Chain of Custody with verified SHA-256 hashes so that our findings remain admissible for HR termination proceedings or civil/criminal litigation."*
* **Human Resources (HR)**:  
  *"As an HR Director, I want documented attribution linking the unauthorized activity directly to account j.doe so that I can execute policy-compliant disciplinary actions."*

---

## ??? Immediate Executive Actions Recommended
1. **Account Containment**: Maintain immediate suspension of all Active Directory, VPN, and physical badge access for j.doe.
2. **Legal Hold**: Preserve all workstation disk images and centralized server logs under formal litigation hold.
3. **Control Remediation**: Authorize immediate enforcement of Multi-Factor Authentication (MFA) on all VPN endpoints and restrict local administrator privileges.
