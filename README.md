<div align="center">

<img src="https://entia.systems/assets/entia_logo_official.png" alt="ENTIA" width="160"/>

# ENTIA Certificates Ledger

**Public, immutable cryptographic ledger for ENTIA Notaría Digital.**

[![eIDAS](https://img.shields.io/badge/eIDAS-EU_Trust_List-22c55e?style=flat-square)](https://entia.systems/compliance)
[![RFC 3161](https://img.shields.io/badge/RFC_3161-Timestamp-3b82f6?style=flat-square)](https://www.rfc-editor.org/rfc/rfc3161)
[![SHA-256](https://img.shields.io/badge/SHA--256-Hash-f59e0b?style=flat-square)](https://entia.systems/notaria)
[![Verify](https://img.shields.io/badge/Verify-entia.systems%2Fnotaria-white?style=flat-square)](https://entia.systems/notaria)

</div>

---

## What This Repository Is

Every document certified by [ENTIA Notaría Digital](https://entia.systems/notaria) generates a **cryptographic certificate** that is committed to this public Git repository. This creates an **immutable, auditable, time-stamped audit trail** that cannot be altered retroactively.

This is not a database — it is a **legal evidence chain** compliant with EU regulation eIDAS (910/2014).

## Certificate Structure

Each certificate file in `/certs/` contains:

```json
{
  "cert_id": "CERT-A1B2C3D4E5F6",
  "file_hash_sha256": "a3f2b8c9d4e5f6...",
  "timestamp_utc": "2026-03-27T10:30:00Z",
  "tsa_provider": "SK ID Solutions (Estonian government)",
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
  → RFC 3161 timestamp requested from SK ID Solutions (EU Trust List TSA)
  → HMAC-SHA256 seal applied with ENTIA signing key
  → Certificate committed to this Git repository (immutable)
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

## Standards Compliance

| Standard | Compliance |
|---|---|
| **eIDAS** | EU Regulation 910/2014, Articles 41-42 (qualified timestamps) |
| **ETSI EN 319 421** | Policy and security requirements for TSA |
| **RFC 3161** | Internet X.509 PKI Time-Stamp Protocol |
| **SHA-256** | NIST FIPS 180-4 hash algorithm |
| **HMAC-SHA256** | RFC 2104 keyed-hash message authentication |
| **GDPR** | EU Regulation 2016/679 (no personal data in certificates) |
| **EU AI Act** | Regulation 2024/1689 (data provenance for AI systems) |

## Why Git as a Ledger?

1. **Immutable** — Git commits cannot be altered without changing all subsequent hashes
2. **Public** — Anyone can clone and verify the entire certificate chain
3. **Time-stamped** — Git commit timestamps + RFC 3161 provide dual temporal proof
4. **Auditable** — Full history available via `git log`
5. **Decentralized** — Mirrors can be created by anyone, GitHub is just the primary host

## Company

**PrecisionAI Marketing OÜ** · Registry 17048063 · EU VAT: EE102780516 · DUNS: 565868914

Sepapaja tn 4, 11415 Tallinn, Harju Maakond, Estonia

🔗 [entia.systems](https://entia.systems) · [LinkedIn](https://www.linkedin.com/company/entia-systems/) · [X](https://x.com/entia_systems) · [API Docs](https://entia.systems/developers)

---

<div align="center">
<sub><em>"Trust requires provenance. ENTIA provides it."</em></sub>
</div>
