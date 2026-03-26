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

## 💡 Purpose

This project focuses on converting real-world attack scenarios into **actionable SIEM detections** rather than just demonstrating tool usage.

---

## ⚠️ Notes

- Designed for portfolio 
- Detection thresholds should be environment-specific  
- Rules should be validated using historical data  
