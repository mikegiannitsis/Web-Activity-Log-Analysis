# Web Activity Log Analysis: Threat Actor Profiling and Attribution

## Overview
Intelligence focused investigation of 2,100+ HTTP requests across a corporate intranet to identify, attribute, and profile a threat actor responsible for unauthorized access attempts. Findings were documented as a structured intelligence report with detection and mitigation recommendations.

| Tool | Purpose |
|------|---------|
| Linux CLI | Log file analysis and filtering |
| VS Code | Log file review and pattern identification |

---
## Objectives
- Analyze a large volume web activity log to establish a traffic baseline and identify anomalous behavior patterns.
- Detect, isolate, and attribute unauthorized access attempts to a specific threat source.
- Profile threat actor behavior by correlating access patterns against legitimate user activity.
- Produce a structured intelligence report documenting findings and recommended detection improvements.

---
## Scenario
A web activity log containing 2,100+ HTTP requests across 77 unique IP addresses was flagged for investigation following reports of suspicious activity on a corporate intranet. The log was analyzed to attribute the threat, profile adversary behavior, and determine the scope and intent of the activity.

---
## Investigation

**Step 1: Baseline Establishment and Scope Assessment**

The log file was reviewed to establish the full scope of activity, 2,100+ HTTP requests originating from 77 unique IP addresses over the monitoring period. A baseline of normal traffic patterns was established to provide context for anomaly identification.

<img width="975" height="789" alt="image" src="https://github.com/user-attachments/assets/4666efb6-a88d-45c7-bae0-2dd3e241a33b" />

**Step 2: Anomaly Detection and Threat Source Isolation**

The log was filtered to surface HTTP 401 Unauthorized error codes, identifying repeated failed authentication attempts as the primary indicator of malicious activity. 68 unauthorized access attempts were detected, all originating from a single IP address, isolating it as the sole threat source among the 77 IPs present in the log.

**Step 3: Threat Actor Behavior Profiling**

Access patterns from the threat source IP were correlated against the baseline of legitimate user behavior across the remaining 76 IP addresses. The volume, frequency, and timing of 401 errors from the single source IP were inconsistent with normal user activity, confirming the behavior as an automated or deliberate unauthorized access campaign consistent with MITRE ATT&CK T1110 (Brute Force) and T1190 (Exploit Public Facing Application).

**Step 4: Intelligence Report Production**

All findings were documented including threat source attribution, scope of unauthorized access attempts, behavioral analysis, and recommended detection and mitigation tactics for review by the security team.

---
## Intelligence Summary

| Finding | Detail |
|---------|--------|
| Log Volume | 2,100+ HTTP requests across 77 unique IP addresses |
| Threat Attribution | Single IP responsible for all unauthorized access attempts |
| Unauthorized Attempts | 68 failed authentication attempts returning HTTP 401 errors |
| Behavior Assessment | Automated or deliberate brute force campaign inconsistent with legitimate user activity |
| MITRE ATT&CK Mapping | T1110 Brute Force, T1190 Exploit Public Facing Application |

---
## Detection Recommendations
- Implement immediate IP blocking for the identified threat source
- Create SIEM alerts triggering on three or more consecutive 401 errors from a single IP within a defined time window
- Deploy rate limiting on authentication endpoints to disrupt automated access attempts
- Review access controls and authentication policies across the corporate intranet
- Expand log monitoring to include HTTP 403 Forbidden errors to broaden threat actor visibility

---
## Skills Demonstrated
`Threat Intelligence` `Threat Actor Profiling` `Attribution Analysis`
`MITRE ATT&CK Mapping` `Log Analysis` `Anomaly Detection`
`Intelligence Reporting` `Linux CLI` `IOC Identification`
`Mitigation Recommendations`
