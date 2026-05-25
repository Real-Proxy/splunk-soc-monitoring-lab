# Security Findings

---

# SSH Monitoring Findings

- Large numbers of failed SSH login attempts were observed.
- Several source IPs generated unusually high authentication activity.
- Certain destination servers received significantly higher SSH traffic volumes.
- Authentication failure patterns indicated potential brute-force behavior.

---

# HTTP Monitoring Findings

- Extremely high numbers of HTTP 404 responses were detected.
- Multiple source IPs demonstrated reconnaissance-style scanning behavior.
- OWASP DirBuster activity was successfully identified.
- Heavy usage of HEAD requests suggested automated enumeration attempts.
- Specific destination servers were heavily targeted by web requests.

---

# Overall Observations

The project successfully demonstrated:
- SIEM log ingestion
- Field extraction and parsing
- SPL-based detection engineering
- Security dashboard creation
- Threat hunting workflows
- Attack visualization techniques

The dashboards provide visibility into both infrastructure-focused and web-focused attack activity using Splunk Enterprise.