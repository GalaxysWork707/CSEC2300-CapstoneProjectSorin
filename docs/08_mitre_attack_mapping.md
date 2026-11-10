# Day 10: MITRE ATT&CK Framework Mapping

**Case**: Lone Star Energy Ops Insider Threat Investigation  
**Date**: 2026-11-10  
**Investigator**: Sorin Rodriguez  
**Document ID**: docs/08_mitre_attack_mapping.md  

---

## ??? Adversary TTP Mapping

This document maps all observed rogue employee actions (j.doe) directly to standard industry tactics, techniques, and procedures (TTPs) defined by the **MITRE ATT&CK Enterprise Matrix**.

| Tactic | Technique Name | Technique ID | Observed Evidence & Activity |
| :--- | :--- | :--- | :--- |
| **Initial Access** | Valid Accounts | T1078 | Used valid employee credentials to log into enterprise VPN off-hours. |
| **Execution** | Command and Scripting Interpreter: PowerShell | T1059.001 | Ran elevated PowerShell scripts on Workstation-04 for privilege discovery. |
| **Privilege Escalation** | Exploitation for Privilege Escalation | T1068 | Escalated local domain rights to full SYSTEM administrative privileges. |
| **Collection** | Archive Collected Data | T1560 | Compressed SCADA telemetry files into hidden .tar.gz archive for staging. |
| **Exfiltration** | Exfiltration Over Alternative Protocol: SSH | T1048.002 | Established outbound SSH tunnel (10.0.4.12 -> 45.33.32.156) to exfiltrate data. |
| **Defense Evasion** | Impair Defenses: Clear Windows Event Logs | T1562.002 | Executed wevtutil cl System to obliterate local audit logs. |

---

## ?? Summary of Threat Vectors
1. **Primary Entry**: Abuse of valid user privileges (T1078).
2. **Impact Category**: Unauthorized data exfiltration (T1048.002) combined with log tampering (T1562.002).
