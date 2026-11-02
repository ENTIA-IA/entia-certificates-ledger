<div align="center">

<img src="https://entia.systems/assets/entia_logo_official.png" alt="ENTIA" width="160"/>

# ENTIA Certificates Ledger

**Public Git record of cryptographic evidence for ENTIA Notaría Digital. Not a register of ISO certifications or government accreditations.**

[eIDAS framework and actual verification requirements](https://digital-strategy.ec.europa.eu/en/policies/eu-trusted-lists)
[![RFC 3161](https://img.shields.io/badge/RFC_3161-Timestamp-3b82f6?style=flat-square)](https://www.rfc-editor.org/rfc/rfc3161)
[![SHA-256](https://img.shields.io/badge/SHA--256-Hash-f59e0b?style=flat-square)](https://entia.systems/notaria)
[![Verify](https://img.shields.io/badge/Verify-entia.systems%2Fnotaria-white?style=flat-square)](https://entia.systems/notaria)

</div>

---

## What This Repository Is

This repository publishes selected cryptographic certificate metadata associated with [ENTIA Notaría Digital](https://entia.systems/notaria). The Git history is reviewable and hash-linked, but **a repository administrator can rewrite Git history**. Independent verification of the evidence and any qualified timestamp must be performed separately.

The presence of metadata in this repository alone is **not** proof of legal validity under eIDAS. Legal effects depend on the actual signed or time-stamped artefact, trust-service status at the relevant time, and an independent validation of that evidence.

## Certificate Structure

Each certificate file in `/certs/` may include fields like those in this **illustrative** example (example values do not prove a live seal):

```json
{
  "cert_id": "CERT-A1B2C3D4E5F6",
  "file_hash_sha256": "a3f2b8c9d4e5f6...",
  "timestamp_utc": "2026-03-27T10:30:00Z",
  "tsa_provider": "Provider stated by the actual verified timestamp",
  "hmac_seal": "HMAC-SHA256:7f8a9b0c1d2e...",
  "entity_id": "E-ES-DEN-12345678",
  "status": "CERTIFIED",
  "eidas_reference": "eIDAS (EU) 910/2014, Art. 41-42"
}
```

## Legal Chain

```
Document submitted
  → SHA-256 hash computed
  → RFC 3161 timestamp requested from the configured TSA, if enabled
  → HMAC-SHA256 seal applied with ENTIA signing key
  → Certificate metadata committed to this Git repository (versioned)
  → Certificate ID returned to client
  → Verifiable at entia.systems/notaria
```

## Verification

Anyone can verify a certificate:

```bash
# Via API
curl https://entia.systems/api/notaria/verify/CERT-A1B2C3D4E5F6

# Via web
# Visit https://entia.systems/notaria and enter the cert_id
```

## Standards and legal references (not independent certifications)

| Reference | Technical relevance / verification requirement |
|---|---|
| **eIDAS** | EU framework; independently verify the exact trust service and qualification status for each applicable timestamp |
| **ETSI EN 319 421** | Technical requirements applying to time-stamping service providers; not a claim of ENTIA certification |
| **RFC 3161** | Protocol reference for timestamp token validation, when a token exists |
| **SHA-256** | Hashing algorithm reference; check digest independently |
| **HMAC-SHA256** | Message authentication reference; independent third parties cannot verify a secret-key HMAC without a suitable verification process |
| **GDPR** | Applicable data-protection obligations must be evaluated separately; this table is not a compliance declaration |
| **EU AI Act** | Possible governance context only; no assertion of certified compliance |

## Why Git as a Ledger?

1. **Tamper-evident** — modifying commits changes hashes; Git branch history is not immutable and requires independent anchoring for stronger assurances
2. **Public** — Anyone can clone and verify the entire certificate chain
3. **Temporal evidence** — Git commit timestamps are repository metadata; qualified legal time evidence requires a separately validated trusted timestamp where present
4. **Auditable** — Full history available via `git log`
5. **Decentralized** — Mirrors can be created by anyone, GitHub is just the primary host

## Company

**PrecisionAI Marketing OÜ** · Estonian registry code 17048063 · DUNS: 565868914 · VAT status: [see the company's dated corporate-status notice](https://entia.systems/legal/en/corporate-status) (former VAT number is historical, not a current identifier)

Sepapaja tn 4, 11415 Tallinn, Harju Maakond, Estonia

🔗 [entia.systems](https://entia.systems) · [LinkedIn](https://www.linkedin.com/company/entia-systems/) · [X](https://x.com/entia_systems) · [API Docs](https://entia.systems/developers)

---

<div align="center">
<sub><em>"Trust requires provenance. ENTIA provides it."</em></sub>
</div>
