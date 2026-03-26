# Brute Force / Credential Stuffing Detection

## Objective
Identify repeated failed authentication attempts that may indicate brute force, password spraying, or credential stuffing activity.

## Threat scenario
An attacker attempts repeated sign-ins against one or many user accounts from one or several IP addresses.
The goal may be:
- account takeover
- password spraying
- validating stolen credentials

## Data sources
- `SigninLogs`
- Optional IP reputation data
- Optional user risk context

## Detection logic
This detection looks for:
- multiple failed sign-ins in a short period
- repeated attempts across multiple users from the same IP
- suspicious concentration of failure activity

## MITRE ATT&CK
- **T1110** – Brute Force

## Investigation steps
1. Validate whether the source IP is internal, external, or anonymous infrastructure.
2. Check whether the affected users are privileged or high-risk accounts.
3. Review whether the activity led to a later successful sign-in.
4. Correlate with MFA prompts, impossible travel, or risky sign-in events.
5. Block, challenge, or monitor the IP depending on policy.

## Tuning ideas
- Exclude trusted identity providers or known monitoring sources.
- Use per-user and per-IP baselining.
- Separate password spraying from true brute force patterns.
- Add geo and ASN enrichment to improve triage.

## Expected outcome
This rule should help analysts identify early-stage account attacks while minimising alert fatigue.
