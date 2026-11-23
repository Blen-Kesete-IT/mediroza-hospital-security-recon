# Evidence Index

Use this file to track reviewed, redacted evidence without storing sensitive source material in the repository.

| Evidence ID | Description | Collection date | Storage reference | Redacted for Git? |
|---|---|---|---|---|
| EVD-001 | Initial Nmap output for 199.188.201.16 | 2026-11-23 (per output) | Controlled local evidence store | Yes — summary only |

## Evidence handling
- Keep original raw scan output in access-controlled storage.
- Review all evidence for credentials, tokens, personal information, patient data, and internal-only details before committing.
- Never commit patient records, staff personal data, passwords, private keys, session cookies, or authentication artifacts.
- Record SHA-256 hashes of original evidence in a separate controlled record if chain-of-custody requirements apply.
- Limit access to authorized project members.
