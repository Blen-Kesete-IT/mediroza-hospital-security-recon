# Preliminary Findings Register

**Assessment stage:** Initial reconnaissance  
**Evidence base:** User-supplied Nmap 7.94SVN output  
**Important:** These are observations and validation leads, not confirmed vulnerabilities.

| ID | Observation | Initial classification | Priority | Status |
|---|---|---|---|---|
| RECON-001 | FTP service identified on TCP/21 (Pure-FTPd) | Service exposure | Review | Observed; configuration unknown |
| RECON-002 | SMTP listeners reported on TCP/25, 26, 465, 587 | Service exposure | Review | Partially identified; TCP/25 unresolved |
| RECON-003 | DNS identified on TCP/53 (BIND response) | Service exposure | Review | Exact version/configuration unknown |
| RECON-004 | OpenResty identified on TCP/80 and 443 | Technology fingerprint | Informational | Observed |
| RECON-005 | Dovecot services on TCP/110, 143, 993, 995 | Service exposure | Review | Configuration unknown |
| RECON-006 | robots.txt lists /patient/, /staff/, /old/ | Public path disclosure | Review carefully | Names observed; access not tested |
| RECON-007 | HTTP/HTTPS probes returned administrative 403 | Access-control behavior | Informational | Observed |
| RECON-008 | Reverse DNS and SMTP banner disclose hosting hostnames | Infrastructure metadata | Informational | Observed |
| RECON-009 | TLS certificate subject, SANs, and validity dates identified | Certificate metadata | Informational | Observed; TLS posture not assessed |

## Validation and closure criteria

A finding may be marked **Confirmed** only when reproducible evidence establishes a security weakness and its impact. Record:
- Evidence reference and timestamp
- Exact affected asset and service
- Safe reproduction method within written authorization
- Expected versus actual behavior
- Impact and realistic likelihood
- Remediation recommendation
- Retest result

Do not infer CVEs solely from a banner. Confirm the exact product build, vendor backports, and applicability before associating a vulnerability identifier or severity.

## Priority note
“Review” is a work-priority label, not a CVSS severity rating. No CVSS score is assigned at this stage.
