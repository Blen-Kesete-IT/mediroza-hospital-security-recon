# Scope and Rules of Engagement

## Target referenced by current evidence
- Domain: `medirozahospital.com`
- IPv4: `199.188.201.16`

These identifiers are transcribed from user-provided scan output. Their inclusion does not itself establish authorization to test them.

## Authorization gate
Before additional active testing, retain written authorization identifying:
- The organization or asset owner granting permission
- Exact domains, IPs, and services in scope
- Approved dates and testing windows
- Permitted and prohibited techniques
- Emergency contact and stop-work procedure
- Data-handling, retention, and disclosure requirements

If authorization is absent or unclear, limit work to passive research and analysis of already-collected evidence.

## Sensitive-data safeguards
- Never access, collect, download, or store patient records or staff account data.
- Do not attempt login, password guessing, mailbox access, or portal enumeration involving real users.
- Do not upload secrets, credentials, private keys, cookies, or personal data.
- Redact sensitive values from logs and screenshots before committing.
- Restrict repository collaborators to the minimum necessary.
- Review Git history before any future visibility change; deleting a file does not erase its prior commits.

## Reporting rules
Use the labels **Observed**, **Hypothesis**, **Needs validation**, and **Confirmed** accurately. Do not label an open port, banner, robots.txt entry, or generic 403 response as a vulnerability without evidence of security impact.
