# Day 13: Policy & Control Recommendations & NIST CSF Alignment

**Case**: Lone Star Energy Ops Insider Threat Investigation  
**Date**: 2026-11-17  
**Investigator**: Sorin Rodriguez  
**Document ID**: docs/11_policy_recommendations.md  

---

## ??? Security Governance & Framework Alignment

To ensure long-term corporate accountability and prevent recurrence of the insider threat incident involving j.doe, Lone Star Energy Ops must adopt a defense-in-depth posture aligned with **NIST CSF 2.0** and **CIS Controls v8**.

### 1. NIST CSF 2.0 Core Functions Integration
* **Govern (GV)**: Establish formal insider threat awareness programs and clear separation of duties for Junior System Administrators.
* **Protect (PR)**: Enforce mandatory Multi-Factor Authentication (MFA) across all remote VPN gateways and enforce Principle of Least Privilege (PoLP) on SCADA networks.
* **Detect (DE)**: Implement automated Data Loss Prevention (DLP) alerts for compressed archive staging and anomalous off-hours terminal executions.
* **Respond (RS)**: Ensure immutable, centralized log shipping to prevent local event log clearing (wevtutil).
* **Recover (RC)**: Establish rapid account containment and cryptographic evidence preservation workflows.

### 2. CIS Controls Alignment
* **CIS Control 5 (Account Management)**: Inventory and audit privileged user accounts on a bi-weekly basis.
* **CIS Control 8 (Audit Log Management)**: Ensure all critical endpoints stream logs to a centralized SIEM in real-time, preventing local tampering.

---

## ?? Agile Stakeholder User Stories (Compliance & CISO)

* **Chief Information Security Officer (CISO)**:  
  *"As a CISO, I want security recommendations mapped directly to NIST CSF 2.0 and CIS Controls so that our organizational risk posture satisfies regulatory and audit requirements."*
* **Compliance & Policy Officer**:  
  *"As a Compliance Officer, I want formal access control policies and mandatory MFA enforcement documented so that we prevent unauthorized cross-segment movement into operational technology."*
