# API Attack Detection with ModSecurity and Wazuh

This repository documents a network security monitoring course project focused on detecting API attacks in a controlled lab environment. The project combines OWASP ZAP, crAPI, ModSecurity, and Wazuh to simulate API attack scenarios, generate security logs, and visualize alerts on a centralized monitoring dashboard.

> Ethical note: all testing was performed in a local lab using OWASP crAPI. The repository focuses on monitoring, detection, and defensive analysis.

## Project Scope

- Deployed a vulnerable API lab using Docker and OWASP crAPI.
- Configured OWASP ZAP as a proxy/testing tool to capture and replay API requests.
- Integrated Apache reverse proxy with ModSecurity to inspect API requests.
- Built custom ModSecurity rules to detect suspicious API behavior.
- Used Wazuh to collect ModSecurity logs, analyze events, and display alerts.
- Evaluated detection scenarios for common API risks such as BOLA, brute force, Broken Authentication, BOPA, NoSQL Injection, and high-frequency request/DoS behavior.

## My Role

**Environment Setup and API Security Testing Contributor**

- Set up the testing environment, including OWASP ZAP Proxy, Docker, and OWASP crAPI.
- Configured request capture and API testing workflows.
- Performed testing and detection validation for NoSQL Injection and high-frequency request/DoS scenarios.
- Documented findings and contributed to the final technical report.

## Architecture

```text
Client / OWASP ZAP
        |
        v
Apache Reverse Proxy + ModSecurity
        |
        v
OWASP crAPI
        |
        v
ModSecurity Audit Logs -> Wazuh Agent -> Wazuh Manager/Dashboard
```

## Tools Used

- OWASP ZAP
- OWASP crAPI
- Docker / Docker Compose
- Apache Reverse Proxy
- ModSecurity
- Wazuh
- Linux

## Detection Scenarios

| Scenario | Security Focus | Monitoring Goal |
|---|---|---|
| BOLA | Unauthorized object access | Detect access to another user's object/resource |
| API Login Brute Force | Broken Authentication | Detect repeated failed login attempts |
| OTP Brute Force | Weak authentication flow | Detect repeated OTP verification attempts |
| BOPA | Unauthorized property manipulation | Detect suspicious business-logic state changes |
| NoSQL Injection | Injection attack | Detect abnormal JSON/operator patterns in API input |
| DoS/Fuzzing | Resource exhaustion | Detect high-frequency requests to sensitive endpoints |

## Key Takeaways

- API security monitoring requires both request-level inspection and centralized log analysis.
- ModSecurity can detect suspicious API behavior when rules are mapped to endpoint, method, request body, and request frequency.
- Wazuh improves visibility by collecting logs and presenting alerts in a dashboard for monitoring and investigation.
- Detection rules should be tuned carefully to reduce false positives and adapt to real application behavior.

## Skills Demonstrated

- API security testing
- Network security monitoring
- OWASP ZAP request capture and testing
- Docker-based lab deployment
- ModSecurity rule design
- Wazuh log monitoring and alert analysis
- Technical reporting

## Repository Contents

- `project_profile_public.pdf`: public project profile for GitHub/CV use.
- `PROJECT_SUMMARY.md`: concise project summary and contribution notes.
- `CV_DESCRIPTION.md`: CV-ready descriptions in English and Vietnamese.
- `PUBLICATION_NOTES.md`: checklist for safe public publishing.

## Disclaimer

This project is for education and authorized security practice only. Do not test, scan, or attack systems without explicit permission.
