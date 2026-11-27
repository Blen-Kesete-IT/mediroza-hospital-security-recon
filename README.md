# Mediroza Hospital — SOC and External Security Reconnaissance

> **Educational, authorized assessment.** This repository presents security observations and defensive analysis, not evidence of compromise. Share publicly only with permission from the project owner and after checking all repository history for confidential information.

## Overview
This project documents a black-box reconnaissance exercise with a SOC analyst's defensive perspective. Evidence includes DNS enumeration, WHOIS, Nmap/Zenmap, infrastructure mapping, web technology fingerprinting, browser TLS inspection, and HTTP/session security observations.

**Project status:** Reconnaissance and preliminary configuration review. **Verified exploitation:** None. **Patient data recovered:** None.

## Evidence and screenshots

[Browse the screenshot evidence index](evidence/SCREENSHOT-GALLERY.md) and [evidence tracking notes](evidence/evidence-index.md).

Images should be stored under `evidence/screenshots/` with sequential descriptive names and displayed in the gallery. Do not upload original session IDs, credentials, records, or confidential documents.

## Observations

| Area | Evidence | Analyst interpretation |
|---|---|---|
| DNS/WHOIS | WHOIS, DNSRecon, NSLookup, Maltego | Maps infrastructure; not a vulnerability by itself |
| Network | Nmap, Zenmap | 80/443 accessible in multiple runs; most scanned ports filtered |
| Web stack | WhatWeb and server banners | Fingerprints may vary with virtual host or proxy layer |
| HTTPS | Browser TLS and headers | TLS enabled; HSTS configuration requires site-specific review |
| Sessions | Firefox Storage | Cookie flags observed; risk requires context and validation |
| Authentication | Staff login screenshot | Login page discovered; no restricted access verified |

## SOC use cases to develop
- Correlate bursts of destination-port probes in firewall/IDS logs.
- Alert on atypical spikes in authentication failures.
- Review abnormal web requests, HTTP 403 bursts, and WAF events.
- Audit access to sensitive files with authorized application logs.

These are proposed detection scenarios, **not confirmed security incidents**.

## Tools
WHOIS · DNSRecon · NSLookup · Maltego · Nmap · Zenmap · WhatWeb · WAFW00F · Firefox Developer Tools.

## Repository structure
- `scope/scope.md` — authorization and handling guidance
- `reconnaissance/01-initial-nmap-scan.md` — baseline findings
- `findings/findings-register.md` — preliminary findings, validation status
- `evidence/SCREENSHOT-GALLERY.md` — visual evidence index
- `evidence/evidence-index.md` — evidence-handling notes

## Disclaimer
All testing must be authorized, scoped, and non-disruptive. Screenshots are security observations as of November 2026. No credential theft, login bypass, or data exposure is asserted. Do not publish protected patient/staff information. Before making this repository public, inspect all files **and Git history**, and get permission to disclose target-specific details.
