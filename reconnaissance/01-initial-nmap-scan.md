# 01 — Initial Nmap Scan

## Scan metadata
- Tool: Nmap 7.94SVN
- Target: `199.188.201.16`
- Reverse DNS: `server274-1.web-hosting.com`
- Scan date embedded in output: 2026-11-23
- Duration: 719.84 seconds
- Reported result: host up; 12 open TCP ports; 988 filtered TCP ports

## Observed services

| Port/TCP | Nmap service | Banner / identification |
|---:|---|---|
| 21 | FTP | Pure-FTPd |
| 25 | SMTP | Connection could not be established by SMTP script |
| 26 | SMTP | Exim smtpd 4.100.1 |
| 53 | domain | BIND identification response; exact version unknown |
| 80 | HTTP | OpenResty 1.31.1.1 |
| 110 | POP3 | Dovecot pop3d |
| 143 | IMAP | Dovecot imapd |
| 443 | HTTPS | OpenResty 1.31.1.1 |
| 465 | SMTPS | Exim smtpd 4.100.1 |
| 587 | SMTP submission | Exim smtpd 4.100.1 |
| 993 | IMAPS | Dovecot imapd |
| 995 | POP3S | Dovecot pop3d |

## HTTP observations
- Port 80 title indicated a redirect to `https://medirozahospital.com/`.
- HTTP and HTTPS probes returned an administrative `403 Forbidden` response.
- Several malformed protocol probes returned `400 Bad request`.
- robots.txt disclosed these path strings: `/patient/`, `/staff/`, and `/old/`.

These path names do not prove that the paths are accessible or contain sensitive data. Do not attempt to access patient or staff information.

## SMTP observations
The Exim banner on ports 26, 465, and 587 identified the SMTP hostname as `server274.web-hosting.com`. Advertised capabilities included STARTTLS on ports 26 and 587, and AUTH PLAIN/LOGIN on port 465. Advertised AUTH mechanisms alone do not establish that credentials are accepted without encryption.

Port 25 was reported open, but the SMTP NSE script could not establish a connection. Treat its service identification as unresolved.

## TLS certificate observation
- Subject CN: `medirozahospital.com`
- SANs: `medirozahospital.com`, `www.medirozahospital.com`
- Not-before: 2026-08-14 20:59:46 UTC
- Not-after: 2027-02-28 21:05:45 UTC

Certificate dates and names were reported by the supplied scan. This output alone does not assess protocol versions, cipher strength, chain validity, or hostname validation.

## Initial interpretation
The host exposes web, DNS, FTP, SMTP, IMAP, and POP3 services. The reverse-DNS and SMTP hostnames suggest a hosted mail/web environment, but shared-hosting status and account isolation are not proven by this scan.

No confirmed vulnerability or compromise is established by these observations.

## Validation questions
1. Is the DNS service authoritative only, or does it also offer recursion?
2. Are DNS zone transfers appropriately restricted?
3. Is FTP protected by TLS, and is anonymous access disabled?
4. Are SMTP relay and authentication policies correctly configured?
5. Do IMAP/POP3 require encryption for authentication?
6. Which TLS versions and cipher suites are enabled?
7. What explains the administrative 403 responses?
8. Are any disclosed web paths intentionally public? Do not inspect patient/staff content.

## Evidence provenance
Source: Nmap output supplied in the project conversation. Preserve the original raw output in a controlled evidence store; commit only reviewed and redacted copies.
