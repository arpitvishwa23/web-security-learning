# A09:2025 – Security Logging and Alerting Failures

## Overview
Security Logging and Alerting Failures occur when applications do not properly record security events, monitor suspicious activities, or generate alerts when attacks happen. Without effective logging and alerting, organizations may not detect breaches for a long time, making incident response and forensic investigations difficult.

This category remains at #9 in the OWASP Top 10:2025 list and highlights the importance of visibility into security events.

---

## Why It Matters
Logging and monitoring help security teams:

- Detect attacks and unauthorized access
- Investigate security incidents
- Identify suspicious user behavior
- Meet compliance requirements
- Improve incident response

Without proper logging and alerting, attackers can remain undetected for months or even years.

---

## Common Causes

Applications may be vulnerable when:

- Failed login attempts are not logged
- Security events are logged inconsistently
- Logs can be modified or deleted by attackers
- Monitoring systems are missing or ineffective
- Alert thresholds are not configured properly
- Security alerts are ignored or not reviewed
- Sensitive information is stored in logs
- Logging systems are vulnerable to injection attacks
- Errors and exceptions are not properly recorded
- Incident response procedures are missing

---

## Impact

Successful exploitation can lead to:

- Delayed breach detection
- Difficulty investigating incidents
- Loss of forensic evidence
- Regulatory compliance violations
- Extended attacker access
- Increased financial and reputational damage

---

## Prevention Measures

To reduce Security Logging and Alerting Failures:

1. Log all important security events.
2. Record successful and failed authentication attempts.
3. Monitor access control failures.
4. Protect logs from unauthorized modification.
5. Store logs securely and maintain backups.
6. Configure alerting for suspicious activities.
7. Avoid storing sensitive information in logs.
8. Implement centralized log management.
9. Create incident response procedures.
10. Regularly review and test monitoring systems.

---

## Example Scenarios

### Scenario 1: Undetected Data Breach
A healthcare provider fails to monitor access logs. Attackers access sensitive patient records for several years before the breach is discovered.

### Scenario 2: Cloud Service Breach
A third-party cloud provider experiences a breach, but delayed monitoring and alerting prevent immediate detection, increasing the impact.

### Scenario 3: Payment System Attack
Attackers exploit vulnerabilities in an online payment system. Due to weak logging and monitoring, malicious activity remains unnoticed until customer data is stolen.

---

## Key Takeaways

- Logging is essential for detecting security incidents.
- Monitoring helps identify suspicious activities quickly.
- Alerting enables rapid response to attacks.
- Logs should be protected and regularly reviewed.
- Strong logging and alerting reduce the impact of security breaches.

---

## References

- OWASP Proactive Controls – Logging and Monitoring
- OWASP Application Security Verification Standard (ASVS)
- OWASP Logging Cheat Sheet
- NIST Incident Response Guidelines

---

## Conclusion

Security Logging and Alerting Failures occur when organizations lack visibility into security events. Proper logging, monitoring, and alerting help detect attacks early, support investigations, and improve overall security posture. Every application should implement effective logging and incident response processes to minimize security risks.