# Lateral Movement / Internal Reconnaissance Detection

## Objective
Detect abnormal internal access behaviour that may suggest lateral movement, discovery, or early-stage post-compromise activity.

## Threat scenario
An attacker who has gained a foothold attempts to:
- connect to multiple hosts in a short period
- enumerate internal services
- authenticate broadly across systems
- move laterally using remote services

## Data sources
- Endpoint process or connection telemetry
- Firewall / network flow logs
- Authentication logs
- EDR events

## Detection logic
This detection looks for:
- one source host reaching many destination hosts
- unusual port spread or connection burst patterns
- repeated authentication attempts across multiple systems
- remote admin protocols used from non-admin systems

## MITRE ATT&CK
- **T1021** – Remote Services
- **T1018** – Remote System Discovery
- **T1046** – Network Service Scanning

## Investigation steps
1. Identify the source device owner and criticality.
2. Review processes associated with the network activity.
3. Check whether the source recently triggered malware, phishing, or credential alerts.
4. Determine whether the destination pattern aligns with normal admin tooling.
5. Contain the source host if activity is suspicious and escalating.

## Tuning ideas
- Baseline authorised admin jump hosts.
- Exclude approved vulnerability scanners.
- Focus on non-standard sources initiating admin protocols.
- Use time-window correlation to catch bursts.

## Expected outcome
This rule helps detect behaviour-based attacker movement rather than relying only on known signatures.
