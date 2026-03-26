# 🔐 Security Detection Engineering Lab

Hands-on detection engineering portfolio aligned to **SC-200 concepts** and tailored to roles involving **SIEM engineering, Azure security, KQL, detection logic, and SOC collaboration**.

---

## 🚀 Key Capabilities

- Clear threat scenario descriptions  
- KQL-based detections (Microsoft Sentinel)  
- Splunk SPL queries  
- Sigma rules (cross-platform detection)  
- Investigation guidance  
- Tuning techniques to reduce false positives  
- MITRE ATT&CK mapping  

---

## 📂 Repository Structure
<img width="223" height="131" alt="image" src="https://github.com/user-attachments/assets/4e45d8aa-f94d-4258-976a-1dab1f95afb4" />

---

## 🎯 Use Cases

### 1) Brute Force / Credential Stuffing
Detects repeated failed authentication attempts across one or multiple accounts.

**Data sources**
- Azure AD / Entra ID sign-in logs  
- Identity provider authentication logs  

**MITRE ATT&CK**
- T1110 – Brute Force  

---

### 2) Suspicious Privilege Escalation
Detects unusual role assignments and privilege changes.

**Data sources**
- Azure AD audit logs  
- Microsoft 365 audit events  
- Identity governance / PIM activity  

**MITRE ATT&CK**
- T1078 – Valid Accounts  
- T1098 – Account Manipulation  

---

### 3) Lateral Movement / Internal Reconnaissance
Detects abnormal access patterns and internal movement.

**Data sources**
- Endpoint telemetry  
- Firewall / network logs  
- Authentication logs  

**MITRE ATT&CK**
- T1021 – Remote Services  
- T1018 – Remote System Discovery  
- T1046 – Network Service Scanning  

---

## 🧠 Engineering Focus

This project demonstrates:

- Detection rule design and tuning  
- Log normalisation and enrichment  
- Behaviour-based detection approaches  
- SIEM and log pipeline optimisation

---

## 🔄 Detection Engineering Approach

Each use case in this repository is implemented across multiple platforms to demonstrate a consistent detection engineering approach independent of specific tools.

### Example: Brute Force Detection

The same detection logic is applied across different technologies:

- **KQL (Microsoft Sentinel)**  
  Detects multiple failed authentication attempts over a defined time window.

- **Splunk (SPL)**  
  Aggregates failed login events and identifies abnormal volumes from a single source.

- **Sigma (Detection-as-Code)**  
  Defines a platform-agnostic rule for repeated authentication failures.

- **Sentinel Analytics Rule (YAML)**  
  Translates detection logic into a scheduled alert with threshold, severity, and entity mapping.

---

### Key Principle

The goal is to design detection logic once and implement it consistently across multiple SIEM platforms, ensuring:

- Reusability of detection logic  
- Platform-independent thinking  
- Improved detection coverage  
- Better alignment with real-world security operations  

This reflects a detection engineering mindset rather than tool-specific implementation.
This approach allows detections to be portable, adaptable, and production-ready across different environments.
---

## 🔧 Example Implementations Across Platforms

Below is a simplified example of how the same detection use case is implemented across different tools.

### 🔐 Use Case: Brute Force Detection

#### KQL (Microsoft Sentinel)
Detects multiple failed login attempts from the same IP within a short timeframe.

  {```kql
  SigninLogs
  | where ResultType != 0
  | summarize FailedAttempts = count() by IPAddress
  | where FailedAttempts > 10
  }

---


## 💡 Purpose

This project focuses on converting real-world attack scenarios into **actionable SIEM detections** rather than just demonstrating tool usage.

---

## ⚠️ Notes

- Designed for community use
- Detection thresholds should be environment-specific  
- Rules should be validated using historical data  
