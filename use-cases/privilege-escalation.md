# Suspicious Privilege Escalation Detection

## Objective
Detect unusual or high-risk privilege assignment events that may indicate compromised admin activity, insider threat, or unauthorised role elevation.

## Threat scenario
A user, application, or service principal receives elevated access unexpectedly, such as:
- Global Administrator
- Privileged Role Administrator
- Security Administrator
- custom privileged application role

## Data sources
- `AuditLogs`
- Privileged Identity Management activity
- Identity governance records
- Change management context

## Detection logic
This detection looks for:
- role assignments to sensitive admin roles
- assignments outside normal business hours
- assignments by unusual initiators
- privilege changes affecting service accounts or dormant accounts

## MITRE ATT&CK
- **T1078** – Valid Accounts
- **T1098** – Account Manipulation

## Investigation steps
1. Confirm whether the change was approved and expected.
2. Identify the initiator, source IP, and authentication context.
3. Check whether the account was recently risky or newly created.
4. Review linked incidents, MFA behaviour, and admin session logs.
5. Revoke or review the privilege if the change is not legitimate.

## Tuning ideas
- Maintain a watchlist of sensitive roles.
- Exclude approved automation identities.
- Correlate with ticketing or CAB approvals where possible.
- Alert differently for permanent vs eligible role assignments.

## Expected outcome
This rule improves visibility into identity-centric attack paths and governance failures.
