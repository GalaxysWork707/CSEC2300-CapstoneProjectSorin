# Day 12: Technical Forensic Report & Evidence Synthesis

**Case**: Lone Star Energy Ops Insider Threat Investigation  
**Date**: 2026-11-17  
**Investigator**: Sorin Rodriguez  
**Document ID**: docs/10_technical_forensic_report.md  

---

## ?? Technical Investigation & Scope
This technical report details the digital forensic findings recovered from the local Docker analysis environment (ollama, open-webui, jupyterlab) and enterprise log telemetry pertaining to suspect j.doe on November 2, 2026.

### 1. Evidence Integrity & Cryptographic Verification
To maintain an unbroken Chain of Custody, all forensic image files and log exports were hashed upon ingestion. Refer to [docs/05_evidence_hashes.md](05_evidence_hashes.md) for full baseline verification:
* **server_auth.log**: e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855
* **workstation_04_sys.evtx**: cf23df2207d99a74fbe169e3eba035e633b65d949b20182059d8e75c5b65e72d

### 2. Chronological Attack Reconstruction
As established in [docs/06_incident_timeline.md](06_incident_timeline.md), the attack lifecycle proceeded through four distinct phases:
1. **Initial Access**: Off-hours VPN authentication at 22:14:05 UTC (T1078).
2. **Privilege Escalation**: Local administrative execution via PowerShell at 22:18:40 UTC (T1059.001 / T1068).
3. **Data Staging & Exfiltration**: SCADA telemetry compression (.tar.gz) followed by outbound SSH tunneling to external IP 45.33.32.156 at 23:02:18 UTC (T1560 / T1048.002).
4. **Defense Evasion**: Clearing of local event logs via wevtutil cl System at 23:15:45 UTC (T1562.002).

---

## ?? Agile Stakeholder User Stories (Technical Team)

* **SOC Analyst / Incident Responder**:  
  *"As a Tier 3 Incident Responder, I want centralized log correlation tied directly to SHA-256 evidence hashes so that I can trace lateral movement across the SCADA gateway without compromising data integrity."*
* **Digital Forensics Examiner**:  
  *"As a Forensics Examiner, I want preserved event logs and file artifacts mapped to MITRE ATT&CK TTPs so that our technical attribution stands up to independent technical audit."*
