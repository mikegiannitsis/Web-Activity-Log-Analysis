# Web Activity Log Analysis

## Overview

Investigation of suspicious web activity across a corporate intranet 
by analyzing a log file containing 2,100+ HTTP requests. The goal was 
to identify anomalous behavior, determine the source of unauthorized 
access attempts, and document findings with recommended mitigation tactics.

| Tool | Purpose |
|------|---------|
| Linux CLI | Log file analysis and filtering |
| VS Code | Log file review and pattern identification |

---

## Objectives

- Analyze a large volume web activity log file to identify anomalous 
traffic patterns across a corporate intranet.
- Detect and attribute unauthorized access attempts to a specific 
threat source.
- Correlate access patterns to distinguish malicious activity from 
legitimate user behavior.
- Document findings and recommend detection and mitigation improvements.

---

## Scenario

A web activity log file containing 2,100+ lines of HTTP requests 
across 77 unique IP addresses was flagged for investigation following 
reports of suspicious activity on a corporate intranet. The log was 
analyzed to identify the source and scope of the threat and determine 
appropriate remediation steps.

---

## Investigation

**Step 1 — Log File Review and Scope Assessment**

The log file was opened and reviewed to establish the full scope of 
activity — 2,100+ HTTP requests originating from 77 unique IP addresses 
over the monitoring period. Initial review established a baseline of 
normal traffic patterns to identify outliers.

<img width="975" height="789" alt="image" src="https://github.com/user-attachments/assets/4666efb6-a88d-45c7-bae0-2dd3e241a33b" />


**Step 2 — Anomaly Detection and Filtering**

The log file was filtered to surface HTTP 401 Unauthorized error codes, 
identifying repeated failed authentication attempts as the primary 
indicator of suspicious activity. 68 unauthorized access attempts were 
detected all originating from a single IP address — isolating it as 
the primary threat source among the 77 IPs in the log.

**Step 3 — Access Pattern Correlation**

Access patterns from the suspicious IP were correlated against the 
baseline of legitimate user behavior across the remaining 76 IP 
addresses. The volume, frequency, and timing of the 401 errors from 
the single source IP were inconsistent with normal user activity, 
confirming the behavior as an automated or deliberate unauthorized 
access attempt rather than accidental misauthentication.

**Step 4 — Findings Documentation**

All findings were documented including the identified threat source IP, 
the scope of unauthorized access attempts, behavioral analysis, and 
recommended mitigation tactics for review by the security team.

---

## Findings & Recommendations

| Finding | Detail |
|---------|--------|
| Log Volume | 2,100+ HTTP requests across 77 unique IP addresses |
| Threat Source | Single IP address responsible for all unauthorized attempts |
| Unauthorized Attempts | 68 failed authentication attempts returning HTTP 401 errors |
| Behavior Assessment | Access pattern inconsistent with legitimate user activity — consistent with automated attack or deliberate brute force |

**Recommended Mitigation Tactics:**
- Implement IP blocking for the identified threat source immediately
- Create SIEM alerts triggering on three or more consecutive 401 
errors from a single IP within a defined time window
- Deploy rate limiting on authentication endpoints to slow automated 
access attempts
- Review access controls and authentication policies across the 
corporate intranet
- Expand log monitoring to include additional HTTP error codes 
such as 403 Forbidden to broaden threat visibility

---

## Skills Demonstrated

`Log Analysis` `Threat Detection` `Access Pattern Correlation` 
`Incident Documentation` `Linux CLI` `HTTP Traffic Analysis` 
`IOC Identification` `Mitigation Recommendations`
