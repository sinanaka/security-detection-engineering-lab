# security-detection-engineering-lab

Hands-on detection engineering portfolio aligned to **SC-200 concepts** and tailored to roles involving **SIEM engineering, Azure security, KQL, detection logic, and SOC collaboration**.

This repository demonstrates practical security detection use cases with:
- clear threat scenario descriptions
- KQL-based detections
- investigation guidance
- tuning ideas to reduce false positives
- MITRE ATT&CK mapping

## Repository structure

```text
security-detection-engineering-lab/
├── README.md
├── use-cases/
│   ├── brute-force-detection.md
│   ├── privilege-escalation.md
│   └── lateral-movement.md
├── kql-queries/
│   ├── brute_force.kql
│   ├── privilege_escalation.kql
│   └── lateral_movement.kql
└── .github/
    └── workflows/
        └── markdown-lint.yml
```

## Purpose

This project is designed to show a **detection engineering mindset**, not just tool familiarity.
It focuses on turning security scenarios into actionable detections that can be used by a SOC or security engineering team.

## Covered use cases

### 1) Brute Force / Credential Stuffing
Detects repeated failed authentication attempts from one or many IP addresses against one or more accounts.

**Data sources**
- Azure AD / Entra ID sign-in logs
- Identity provider authentication logs
- Optional threat intelligence enrichment

**ATT&CK**
- T1110 – Brute Force

### 2) Suspicious Privilege Escalation
Detects unusual role assignments, admin privilege grants, or service account privilege changes.

**Data sources**
- Azure AD audit logs
- Microsoft 365 audit events
- Identity governance / PIM activity

**ATT&CK**
- T1078 – Valid Accounts
- T1098 – Account Manipulation

### 3) Lateral Movement / Internal Reconnaissance
Detects abnormal access attempts across multiple hosts, east-west movement, or discovery-style connection patterns.

**Data sources**
- Endpoint telemetry
- Firewall or network flow logs
- Authentication logs

**ATT&CK**
- T1021 – Remote Services
- T1018 – Remote System Discovery
- T1046 – Network Service Scanning

## Notes

- These examples are intentionally written for portfolio and interview demonstration.
- Thresholds should always be tuned against your own environment.
- Detection content should be validated with historical data before production deployment.

## Interview positioning

A useful way to describe this project:

> I built a small detection engineering lab to convert SC-200-style concepts into practical use cases using KQL, MITRE mapping, investigation steps, and alert-tuning logic.

## Next improvements

- Add Sigma equivalents
- Add Sentinel analytics rule YAML
- Add Splunk SPL versions
- Add sample synthetic log data
- Add dashboards and workbook ideas
