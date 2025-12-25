# Alert Triage Playbook

## Alert
- **Name:**
- **Severity:** (Low / Medium / High)
- **Category:** (Authentication / Malware / Phishing / Network / Endpoint)
- **Goal:** What are we trying to confirm or rule out?

## Data Sources
- (e.g., Windows Security Event Logs, Sysmon, EDR, Firewall, Proxy/DNS, Email gateway)

## Triage Checklist (in order)
1) **Validate alert context**
   - What rule triggered? What threshold? What time window?
2) **Identify affected entities**
   - User, host, IP, process, URL, email sender, file hash
3) **Check for benign explanations**
   - Expected admin activity, scheduled task, VPN, password reset, known scanner
4) **Expand scope**
   - Same user on other hosts, same IP across users, same hash across endpoints
5) **Assess impact**
   - Any successful login? privilege change? new persistence? data access?
6) **Decide**
   - True positive / False positive / Needs more info

## Evidence to Capture
- Screenshot(s) or query output
- Key log lines (sanitized)
- Timeline (3–8 key points)

## Escalation Criteria
Escalate to IR if any of:
- Confirmed successful compromise indicators
- Repeated attempts + suspicious tooling
- Persistence, credential dumping, lateral movement, or exfil signals

## Containment Suggestions (if true positive)
- Disable account / reset password
- Isolate host
- Block IP/domain/hash
- Revoke sessions/tokens

## Notes / Tuning
- False positives observed:
- Rule improvements:
