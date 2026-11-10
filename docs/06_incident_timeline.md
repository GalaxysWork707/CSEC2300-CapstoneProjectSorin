# Chronological Incident Timeline

**Case**: Lone Star Energy Ops Insider Threat Investigation  
**Date**: 2026-11-10  
**Investigator**: Sorin Rodriguez  
**Scope**: Timeline reconstruction of compromised account activities and unauthorized access.

---

## Incident Timeline Log

| Timestamp (UTC) | Source System | User / IP | Observed Activity | Forensic Impact & Severity |
| :--- | :--- | :--- | :--- | :--- |
| **2026-11-02 22:14:05** | Auth Server (VPN) | j.doe / 192.168.1.105 | Successful VPN login outside standard working hours | **Informational**: Off-hours authentication anomaly. |
| **2026-11-02 22:18:40** | Workstation-04 | j.doe | Executed local privilege escalation attempt via powershell.exe | **Medium**: Escalation to elevated privileges (SYSTEM). |
| **2026-11-02 22:31:12** | SCADA Gateway | j.doe / 10.0.4.12 | Unauthorized access attempt to restricted SCADA telemetry logs | **High**: Access violation on operational control network. |
| **2026-11-02 22:45:00** | Data Store | j.doe | Compressed sensitive database exports into .tar.gz archive | **High**: Data staging for potential exfiltration. |
| **2026-11-02 23:02:18** | Edge Firewall | 10.0.4.12 -> 45.33.32.156 | Outbound SSH connection established to external IP | **Critical**: Data exfiltration channel initiated. |
| **2026-11-02 23:15:45** | Workstation-04 | j.doe | Executed wevtutil cl System to clear event logs | **High**: Impair defenses / artifact cleanup. |

---

## Technical Summary & Attack Vectors
1. **Initial Access**: Valid credentials used for off-hours VPN entry.
2. **Execution & Escalation**: Scripted execution via PowerShell to obtain elevated rights.
3. **Exfiltration Staging**: Aggregation and compression of sensitive operational data into hidden archives.
4. **Defense Evasion**: Cleared event logs to impede post-incident forensic recovery.
