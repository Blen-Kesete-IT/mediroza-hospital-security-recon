# Mediroza Hospital — External Security Reconnaissance

> **Confidential working repository.** This project contains target-specific infrastructure observations. Keep repository visibility set to **Private** and grant access only to explicitly authorized collaborators.

## Purpose
Document an evidence-led, authorized external security assessment. The current material is an initial Nmap baseline, not a vulnerability report.

## Target profile
| Field | Observation |
|---|---|
| Domain | medirozahospital.com |
| IPv4 | 199.188.201.16 |
| Reverse DNS | server274-1.web-hosting.com |
| SMTP banner hostname | server274.web-hosting.com |
| Scanner | Nmap 7.94SVN |
| Scan date reported | 2026-11-23 |
| Scan duration | 719.84 seconds |

## Initial scope of observations
- Network service exposure and service identification
- DNS and email configuration review
- Web-server and TLS configuration review
- Publicly disclosed web paths

No exploitation, authentication attempts, access to patient/staff data, or intrusive testing is implied by this baseline.

## Repository map
- `scope/scope.md` — authorization and handling rules
- `reconnaissance/01-initial-nmap-scan.md` — scan observations
- `findings/findings-register.md` — preliminary findings and validation status
- `evidence/evidence-index.md` — evidence tracking

## Status
**Stage:** Initial reconnaissance  
**Confirmed vulnerabilities:** None established from the supplied scan  
**Next milestone:** Authorized passive DNS and configuration review

## Handling requirements
- Keep this repository private.
- Do not commit credentials, tokens, private keys, session cookies, patient information, staff personal data, or unredacted sensitive logs.
- Do not place patient portal contents or screenshots in evidence.
- Preserve original evidence securely and record hashes where appropriate.
- Treat banners and software versions as leads; verify before assigning CVEs or severity.
- Obtain written authorization and define testing limits before any active follow-up.

## Disclaimer
All activity must be explicitly authorized and limited to the approved scope. This repository records observations for defensive assessment; it does not assert that the target is vulnerable or compromised.
